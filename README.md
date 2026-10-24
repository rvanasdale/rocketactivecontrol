# Rocket Attitude Control

This repository contains the Teensy 4.1 control code for my fin-tab controlled rocket project. The current program estimates tilt in two directions and moves four servo-driven fin tabs to respond to that tilt.

## How it works

- Reads acceleration and angular velocity from a SparkFun ISM330DHCX IMU.
- Uses two Kalman filters to combine accelerometer tilt estimates with gyroscope measurements and estimate gyro bias.
- Uses a PD controller to calculate corrections from tilt and angular rate.
- Converts those corrections into servo commands, limited to 1000–2000 microseconds.

At startup, the program centers the servos and calibrates the gyroscope while the rocket is stationary. It also centers the servos if sensor readings stop arriving.

## Hardware

- Teensy 4.1
- SparkFun ISM330DHCX IMU connected through Wire2
- SparkFun MPL3115A2 Altimeter connected through Wire1
- Four HV6120 servos connected to pins 2–5
- Custom fin tabs and linkages

## Testing and current status

I have bench-tested servo centering, movement direction, and the controller’s response to changes in IMU orientation. I am also working toward MATLAB-based flight dynamics simulations, along with my previous CFD analysis to refine the aerodynamic model and support controller tuning.

The hardware and control software are assembled and undergoing testing, with flight testing as the next major milestone.

## My work

I developed this rocket project from the initial concept through CAD design, component selection, mechanical assembly, electronics integration, and bench testing. My work includes designing the airframe and fin-control mechanism, integrating the avionics and power system, and working on flight dynamics modeling and controller tuning. 

This repository contains the attitude-control portion of that work. I used ChatGPT to assist with developing and debugging the software, then integrated it with my hardware and tested the sensor readings, servo directions, and response to changes in orientation.

