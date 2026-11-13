---
layout: page
title: Advanced Components
parent: Resources
nav_exclude: false
description: >-
    Advanced Components
---

# Advanced Components
{:.no_toc}

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

# Week 7 components

This page details key information for the new parts introduced in Week 7 that _supplement_ - but do not replace - the readings; their pinout diagrams, how to wire them and control them, and what to watch out for. 

You can access complete datasheets here: [datasheets](https://drive.google.com/drive/folders/1tFlON6RotuLl_CQ2lE-gby_-qjhWu00B?usp=sharing).

---

## 1. Limit switch (KW12-3)

A limit switch looks like a lever, and is typically situated at the end of a rail so that the machine contacts and presses the limit switch at the end of its travel, allowing the Arduino to know where the end (zero/home) location is.

### Annotated photos

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/limit_switch_kw12-3.jpg' | relative_url }}"
       alt="device"
       style="display: block; max-width: 80%; height: auto; margin: 0 auto;">
  <figcaption>Annotated Limit Switch. Left: the side printed 1 3 2. Right: the other side, printed NC NO C (mirrored, so 1 = C). Image: DIYables, via <a href="https://arduinogetstarted.com/tutorials/arduino-limit-switch">ArduinoGetStarted</a>.</figcaption>
</figure>

### Table showing connection options

| Terminal | Name | Joined to C when… |
|---|---|---|
| 1 | C (common) | – |
| 2 | NC (normally closed) | not pressed |
| 3 | NO (normally open) | pressed |

### Limit Switch Schematic

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/limit_switch_schematic.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 80%; height: auto; margin: 0 auto;">
  <figcaption>Limit switch schematic.</figcaption>
</figure>

### Implementation recommendations

- Connect **1 (C) to GND** and **2 or 3 to an Arduino pin** with `INPUT_PULLUP`. Always use terminal 1.
- **1 + 2 (NC) is safer:** a loose wire also reads "pressed", so the machine stops.
- **Check using multimeter contintuity check:** 1–2 beeps when not pressed, 1–3 when pressed.
- It bounces like a button: debounce it.

---

## 2. Servo motor (MS18)

A motor that uses closed-loop control to rotate to an angle on the interval (0–180°) and hold there.

### Table showing connections

| Wire | Connect to |
|---|---|
| Brown | GND (joined to the Arduino's GND) |
| Red | 5V from the buck converter |
| Orange | Any Arduino digital pin |

### How to set Servo angle with pulse width

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/servo_timing.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 80%; height: auto; margin: 0 auto;">
  <figcaption>Servo pulse width and corresponding angle. The pulse width sets the angle: about 1ms = 0°, 1.5ms = 90°, 2ms = 180°, repeated every 20ms. Image: <a href="https://lastminuteengineers.com/servo-motor-arduino-tutorial/">Last Minute Engineers</a></figcaption>
</figure>

### Implementation recommendations

- **Code:** `#include <Servo.h>`, then `myServo.attach(pin)` once and `myServo.write(angle)`.
- **Power it from the buck converter, not the Arduino's 5V pin:** a servo's current spikes can reset the Arduino.
- Push a horn (the plastic arm) onto the shaft to see the angle; don't turn it by hand while powered.
- The `Servo` library turns off `analogWrite` on pins 9 and 10.

---

## 3. Stepper motor (NEMA 17: 17HS15-1504S-X1)

A motor that turns in exact steps: 200 steps per revolution (1.8° each). It always needs a driver; never connect it to the Arduino directly and **always** power from an external supply.

### Stepper motor wiring overview

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/stepper_17HS15-1504S-X1_wiring.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 80%; height: auto; margin: 0 auto;">
  <figcaption>Stepper motor wiring diagram. Image: <a href="https://www.omc-stepperonline.com/download/17HS15-1504S-X1.pdf">StepperOnline 17HS15-1504S-X1 datasheet</a></figcaption>
</figure>

### Table showing connections

| Wire | Coil | Driver pin |
|---|---|---|
| Black | A+ | A1 |
| Green | A− | A2 |
| Red | B+ | B1 |
| Blue | B− | B2 |

### Implementation recommendations

- **Check the coil pairs with a multimeter:** about 2.3Ω across one coil, nothing between coils. Cable colours can differ, so trust the meter.
- Swapping the two wires of one coil (e.g. black and green) only reverses the direction. If it buzzes but doesn't turn, wires from different coils are mixed up.
- **Never plug or unplug the motor while the driver is powered.**
- Specs: 1.5A per phase, 0.45Nm, NEMA 17 (42mm), 5mm D-shaft.
- It always needs a driver; never connect it to the Arduino directly and **always** power from an external supply.

---

## 4. Stepper driver (BIGTREETECH TMC2209 V1.3)

Stepper motor drivers have control circuitry required to control stepper motors. The Arduino sends STEP ("move one step") and DIR ("which way"); the driver handles powering the motor coils.

### Stepper driver Pinouts

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/tmc2209_btt_v1.3_pinout_annotated.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 80%; height: auto; margin: 0 auto;">
  <figcaption>BIGTREETECH TMC2209 V1.3 pinout with pin meanings. Image shows pinout from the BIGTREETECH TMC2209 V1.3 User Manual, page 5; pin meanings added.</figcaption>
</figure>


### Implementation overview & recommendations
- **Always** power the driver/stepper from an external supply, not the Arduino.
- **One revolution = 1600 STEP pulses** (MS1 and MS2 open = 8 microsteps × 200 steps).
- **Breadboard: cut off the DIAG and INDEX pins on the top edge first.** Otherwise they sit in the same breadboard row as EN and short together.
- **Join the adapter's GND and the Arduino's GND;** never join VM and 5V.
- **Never unplug the motor while VM is powered.** The driver gets hot; don't touch it.
- **The current knob.** It sets the motor current. **Clockwise = less current, counter-clockwise = more.** The factory setting (about 0.9A) works for this lab. Change it only if:
    - The motor **skips steps or stalls** under load: turn it a little **counter-clockwise**;
    - The motor or driver gets **too hot to touch**: turn it a little **clockwise**.
    - To check the setting, measure the voltage between GND and the knob's metal centre with the driver powered: current (A) ≈ voltage ÷ 1.41. Don't go above about 1.7V (1.2A) without a fan ([BIGTREETECH wiki](https://global.bttwiki.com/TMC2209.html), V1.3 manual).

---

## 5. Ultrasonic sensor (HC-SR04)

The ultrasonic distance sensor measures distance by timing an ultrasonic echo.


### Pinout

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/hcsr04_pinout.jpg' | relative_url }}"
       alt="device"
       style="display: block; max-width: 60%; height: auto; margin: 0 auto;">
  <figcaption>Pinout for ultrasonic distance sensor HC-SR04. Image: <a href="https://microcontrollerslab.com/ultrasonic-hc-sr04-sensor-arduino-tutorial/">Microcontrollers Lab</a></figcaption>
</figure>

### Timing diagram

<figure style="text-align: center;">
  <img src="{{ '/assets/images/wk7-elec/img/hcsr04_timing.jpg' | relative_url }}"
       alt="device"
       style="display: block; max-width: 60%; height: auto; margin: 0 auto;">
  <figcaption>Timing diagram for ultrasonic distance sensor HC-SR04. Image: <a href="https://microcontrollerslab.com/ultrasonic-hc-sr04-sensor-arduino-tutorial/">Microcontrollers Lab</a></figcaption>
</figure>

### Table showing connections

| Pin | Connect to |
|---|---|
| Vcc | Arduino 5V |
| Trig | Arduino pin (OUTPUT) |
| Echo | Arduino pin (INPUT) |
| GND | Arduino GND |

### Implementation overview & recommendations

- **Measure:** Trig HIGH for 10µs, then `duration = pulseIn(echoPin, HIGH, 30000)` (0 = no echo).
- **Distance (cm) = duration (µs) / 58.**
- Wait at least 60ms between readings, and average a few: they are noisy.
- Range 2cm–4m, in a 15° cone ([Elecfreaks datasheet](https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf)).
