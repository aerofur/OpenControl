# OpenControl
An Open Source Locomotive Control Chip for Garry's Mod built on Wiremod's Expression 2 Environment


## Scope

The scope of the OpenControl Project is to build a robust, light-weight and life-like simulation of a Locomotive, that is [Open Source](https://opensource.com/resources/what-open-source), Open to community contributions, and built by a group of diverse Developers.

![pre-release](https://github.com/TitusStudiosMediaGroup/OpenControl/workflows/pre-release/badge.svg)

## To-Do List
This is a list of what we have to complete, fix, or build. *(These may be out of date)*

  * [ ] Air Braking System
    * [x] Compressor
    * [x] Compressor Logic
    * [x] Main Reservoir
    * [x] Equalising Reservoir
    * [x] Brake Pipe
    * [x] Brake Cut-in/out
    * [x] Trainline 
    * [x] Trainline EOT drop
    * [x] Dynamic Air 
    * [x] Pressure Equalization between MainRes fill up and EQ
    * [x] Pressure Equalization between EQ and BP (depending on BCO setting)
    * [x] Pressure Equalization between BP and TL (MU & Cars, no Cars, MUed, Single)
    * [x] Pressure Equalization logic between all Res's depending on brake piping
    * [x] PCS
    * [x] MainRes air dryer
    * [x] Control Air
    * [x] MainRes "jump" on Bail
    * [x] Locomotive Brake res logic
    * [ ] Air Compressor Pitch up (runs on engine RPM)
      * Base this off the Engine RPM calulations in the Electrical chip (send the engine RPM through the data array).
    * [x] Emergency Braking
    * [x] BP and Trainline "speeds" are now based on how many cars there are. 
      * The more the slower it takes to reach the Feed Pressure.
      * Also means that Emrg Braking takes longer
  * [ ] Physics System / Electrical
    * [x] Playerbased Speed and Physics Calculations
    * [x] MPH
    * [x] KPH
    * [x] WheelSlip
      * [x] Reduce Current when WheelSlip occurs
      * [x] Map Weather Condition FETCH
        * Not yet to be working (Needs lua?). Would set the Friction Coefficient depending on the rail conditions. Is set to 0.5 by default, if they were wet it would be 0.3. Applying sand would counteract this, and set it to 1.0.
    * [ ] Traction Control
      * [x] No Traction Control (Early)
      * [ ] Automatic Power Reduction (Mid)
      * [ ] Automatic Power Reduction and Sand (Late)
      * [ ] Electronic Traction Control (Modern)
    * [x] Traction Motor Overheat
      * [x] Change overheating properties depending on Mechanically-Driven or Electrically-Driven Traction Motor Blowers. See Dynamic Modes.
    * [x] Dynamic Grid Overheat
    * [x] Sanders
    * [x] Slugs & Cab Units (Unit Types)
      * [x] Locomotive
      * [x] Slug (No Prime Mover, has Traction Motors)
      * [x] Snail (No Traction Motors, has Prime Mover)
      * [x] Cab Car/Control Cab (No Traction Motors or Prime Mover)
    * [ ] Generator Transition
      * Need to look into this first.
    * [x] Transition Groups
    * [x] Transition Shunts
    * [x] Dynamic Modes
      * [x] No Dynamics
      * [x] Dynamic Brakes with Mechanically-Driven Traction Motor Blowers
      * [x] Dynamic Brakes with Electrically-Driven Traction Motor Blowers
    * [x] Blended Braking
      * Modern Passenger Thing, turns on dynamic brakes when air brake application is made.
    * [x] Hend-End Power
      * [x] HEP Up Input
      * [x] HEP Down Input
      * [x] Remove horsepower if HEP active (can be set in the config)
    * [x] Dual Prime Mover
    * [x] Primer / Starter Modes
      * [x] Manual Primer, Manual Start
      * [x] Latched Primer, Manual Start
      * [x] Fully Automatic Start
    * [ ] OverloadProtection
      * The locomotive will reduce power if thermal limits of the traction motors are exceeded.
    * [x] Adhesion
    * [x] Custom Load Ramping Speed
      * Will be located in configs, the default should be 15. (see clamps in TM Calc)
    * [x] Low Speed Curve Enable/Disable
    * [ ] Engine Sound Pitch Rise when in MU (Assign in the engine sound control chip)
    * [ ] Cruise Control
      * [ ] Dynamic Cruise Control
      * [ ] Normal Cruise Control
      * Not very keen on doing this.. (Would anyone use it? If its not used much; no point in adding it, wasted cpu time..?) If someone else would like to do it feel free to make a Pull Request, or [Contact me](https://www.titusstudios.net/contact)!
  * [x] User Control
  * [ ] Chat Commands
    * [ ] Autostarting
      * [ ] Single PM
      * [ ] DPM
    * [ ] Shutdown
      * [ ] Single PM
      * [ ] DPM
    * [ ] Automatic Brake
    * [ ] Locomotive Brake
    * [ ] Notch
    * [ ] Dynamics
      * [ ] Dynamic Setup
      * [ ] Dynamics Powerzone (if un-notched dynamics)
    * [ ] Control individual units by their Roadnumber
  * [ ] I/O
    * [x] MU Hose Functionality
      * Convert automatic MU E2 to automatic air hose E2
    * [x] Handbrake
      * Make handbrake e2 that uses `eyeTrace()`, meaning you dont need to use buttons. (E to apply, Shift+E to release)
    * [x] Locomotive Fan E2
      * Adds working fans to the locomotive with sounds. This may be required to have on the locomotive for sounds, otherwise no dyno / fan sounds, etc.
    * [ ] Outputs for External E2s
  * [ ] Control Stand
    * [x] 26L Brake Control Logic
    * [x] Manual Selector
    * [x] Emrg Hotkey
      * Press a key to activate the Emergency Brake, so you dont need to go through the whole braking process
  * [ ] Multiple Units
    * [x] AAR 27 Pin Standard
    * [x] Air System MU
    * [x] MU2A
    * [ ] MU Headlights
    * [x] MU Sanding
  * [x] Configs
  
  
## What can be Multi-Parented

Item | Can be Multi-Parented? |
---|---|
Config | ✔ | 
Control Stand Controller | ✔ | 
Diesel Electric Processor | ❌ | 
Engine Sound Processor | ✔ | 
Locomotive Airbrakes Processor | ✔ | 
Sound Processor | ✔ | 

> NOTE: When installing, remember to rename the folder from "OpenControl-master" or whatever it is to just "OpenControl"

## How it all works

**NOTE:** This explanation is *very* simplified.

## Traction

### DC Traction

The DC Traction system in OpenControl is built on Ohm's Law:

*Ohm's law states that the current through a conductor between two points is directly proportional to the voltage across the two points. Introducing the constant of proportionality, the resistance one arrives at the usual mathematical equation that describes this relationship:*
### *I* = (V/R)

Generator Field Current and the Speed of the Engine (RPM), determines the voltage of the generator.
For most US engines, this is normalised to 600VDC.

 * A Generator, is a motor running in reverse. When you apply a current to the windings of a motor, a magnetic field is induced in the armature of the motor. This magnetic field causes the armature to spin. *(simplified explanation)*.
If you run the motor in reverse, then you will induce a current in the motor windings.

![Motor GIF](/src/figs/GIF/motor.gif)

*GIF provided from Wikipedia, https://en.wikipedia.org/wiki/Electric_motor#/media/File:Electric_motor.gif*

 * Back electromotive force (Back EMF, BEMF) is a voltage that appears in the opposite direction to current flow as a result of the motor's coils moving relative to a magnetic field.

Once we have the Voltage of the Generator, we apply this to the Traction Motors.

The Traction Motor Current is calculated by getting the Generator Voltage (at motor terminals), and subtracting the number of Parallel paths multiplied by the Back EMF of the Traction Motor, which increases linearly to the Speed of the Locomotive.

The final current is determined by dividing the Traction Motor Current by the Resistance of the Motor.
The Resistance of the motor is calculated using Ohm's Law, R = Motor Terminal Voltage divided by the Current.

### Dynamic Braking

This same principle is applied to the Dynamic Brakes.
However the Dynamic Brake Resistor Grid is connected in series with the Traction motors, this will pull power from the Traction Motors, slowing down the Locomotive.

The Dynamic Brake Resistor Grid Resistance is fixed (not including heat losses). OpenControl uses a 700 Amps Dynamic Base line, which is 0.923 Ohm's.

 * A resistor resists the current flow of a circuit, as if you were pushing water through a pipe, and had a smaller pipe at the end. The loss of *"flow"*, is converted from electrical energy into Heat energy. The more current you are *resisting*, the more heat is generated. Depending on the material the resistor is made out of, the resistance will lower as it heats up. The speed of this is dependant on the material.
 
OpenControl uses the Axle RPM, to calculate the voltage of the Traction Motor(s), as if it was a generator.
Then it uses the voltage and Ohm's Law to calculate the Current of the Dynamic Brakes.

The output of this will be a positive, and the code inverts the current output to a negative.

## Logic Flow Charts

![OpenControl Locomotive Air System FIG1](/src/figs/PNG/opencontrol-airsytsemfig1.png)
![OpenControl Locomotive Traction Motor & Electrial System FIG1](/src/figs/PNG/opencontrol-tractioncircuitfig1.png)
![OpenControl Locomotive Traction Curve](/src/figs/PNG/opencontrol-tractioncurve.png)
![OpenControl Locomotive Current Curve](/src/figs/PNG/opencontrol-currentcurve.png)

## Developers & Contributors
We are very grateful for your help with the Project, whether a one time contribution, multiple contributions, or longtime developer.

[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/0)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/0)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/1)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/1)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/2)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/2)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/3)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/3)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/4)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/4)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/5)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/5)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/6)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/6)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/7)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/7)

## Addressing the Elephant in the Room

The OpenControl project is in no way associated with RLC, PT Gamma, PT2, or other variants. OpenControl is solely based on community contributions. OpenControl is neither a re-built, edited, or rebranded version of RLC, nor is this project based on events, which is basing this entire project over "revenge" for said events

OpenControl is in no way associated with RLC, PT Gamma, PT2, or other variants. And is neither a re-built, edited, or rebranded version of RLC.

## Licence

OpenControl is licensed under the: **MIT License**

*A short and simple permissive license with conditions only requiring preservation of copyright and license notices. Licensed works, modifications, and larger works may be distributed under different terms and without source code.*

```
MIT License

Copyright (c) 2020 Titus Studios Media Group

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```


Copyright © 2018-2020 Titus Studios Media. *Terms and Conditions are available on the [TitusStudios Website](https://www.titusstudios.net/)*
