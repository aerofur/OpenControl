# OpenControl
An Open Source Locomotive Control Chip for Garry's Mod built on Wiremod's Expression 2 Environment


## Scope

The scope of the OpenControl Project is to build a robust, light-weight and life-like simulation of a Locomotive, that is [Open Source](https://opensource.com/resources/what-open-source), Open to community contributions, and built by a group of diverse Developers.

## To-Do List
This is a list of what we have to complete, fix, or build. Refer to [Roadmap](#roadmap) for more info.

  * [ ] Air Braking System
    * [x] Compressor
    * [x] Compressor Logic
    * [x] Main Reservoir
    * [x] Equalising Reservoir
    * [x] Brake Pipe
    * [x] Brake Cut-Out Logic
    * [x] Brake Pipe Pressure Loss /time (0.08 ppr1-ppr4)
    * [x] Main Reservoir Pressure Loss /time (0.25 ppr1-ppr4)
    * [ ] Brake Pipe Logic
    * [x] Equalization Function
    * [ ] EOT Pressure Drop
    * [x] Equalising Reservoir ~ Main Reservoir - Pump Logic
    * [x] Equalising Reservoir ~ Brake Pipe - Pump Logic
    * [x] Brake Type Settings (26L / 26C / 6SL / etc)
  * [ ] Traction System
    * [ ] Generator Transition
    * [ ] Traction Motor Transition
    * [ ] AC & DC Motor/Gen Systems
    * [x] Traction Motor Logic
    * [x] Air Brake Force Application
  * [x] Physics System
  * [x] User Control
  * [ ] I/O
    * [ ] MU Hose Functionality
      * Convert automatic MU E2 to automatic air hose E2
    * [ ] Handbrake
      * Make handbrake e2 that uses `eyeTrace()`, meaning you dont need to use buttons. (E to apply, Shift+E to release)
    * [ ] Locomotive Fan E2
      * Adds working fans to the locomotive with sounds. This may be required to have on the locomotive for sounds, otherwise no dyno / fan sounds, etc.
  * [ ] Control Stand
    * [x] 26L Brake Control 
      * [x] 60 sec PCS cutout
      * [x] Brake Position Logic
    * [x] Communitcation between Control Stand and Main Chip
  * [x] Configs
  
  
## Roadmap

We do not have an official *"Done by Date"*, OpenControl is a community contribution based Project, and will not have a dead-end. However, we plan to have the first Beta release complete by, Mid-Late 2020. 

## How it all works

To be added.

![OpenControl Locomotive Air System FIG1](/src/figs/PNG/opencontrol-airsytsemfig1.png)
![OpenControl Locomotive Traction Motor & Electrial System FIG1](/src/figs/PNG/opencontrol-tractioncircuitfig1.png)

## Developers & Contributors
We are very grateful for your help with the Project, whether a one time contribution, multiple contributions, or longtime developer.

[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/0)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/0)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/1)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/1)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/2)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/2)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/3)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/3)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/4)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/4)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/5)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/5)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/6)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/6)[![](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/images/7)](https://sourcerer.io/fame/TitusStudiosMediaGroup/TitusStudiosMediaGroup/OpenControl/links/7)

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
