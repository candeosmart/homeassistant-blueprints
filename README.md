
# Home Assistant Blueprints for Candeo devices #

Devices

1. [RD1-Pro](#rd1-pro-c-zb-rd1p-decoupled-dimming-switch)
2. [Modmote Scene Switches (CMM-1)](#modmote-scene-switch-blueprint)
3. [5 Button Scene Switch with Rotating Dial (C-ZB-SR5BR)](#5-button-scene-switch-with-rotating-dial)



## RD1-Pro (C-ZB-RD1P) Decoupled Dimming Switch ##

**5 Blueprints for the RD1-Pro (C-ZB-RD1P) Decoupled Dimming Switch**

1. [Smart Bulb Control - brightness, white temperature, colour](#control-your-smart-lights-brightness-colour-and-white-temperature--all-from-a-single-switch)
2. [Control the wired circuit and get button events for double press, hold and release](#control-the-wired-circuit-and-get-button-events-for-double-press-hold-and-release)
3. [Activate Scenes from your RD1-Pro](#activate-your-scenes-or-scripts-from-your-wall-switch)
4. [Multi Light control with a single RD1-Pro](#control-3-lights-with-a-single-dimming-switch)
5. [Lights, Music, action](#control-your-speakers-and-your-lights-with-1-wall-dimmer-switch)


### Control your smart lights brightness, colour, and white temperature – all from a single switch. ###

Bring back natural wall control for your smart bulbs without cutting power. This blueprint lets the RD1-Pro knob toggle, dim, warm or cool white, and rotate through colour. It solves the classic problem of app-only control by making the wall control feel modern and reliable again.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-smart-bulb-colour-light-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-smart-bulb-colour-light-control.yaml)



### Control the wired circuit and get button events for double press, hold and release ###

Control your wired lights circuit, and get button events by putting the device in DPM mode and using the Remote (Endpoint2) to control the dimmable light on Endpoint1.

**ZHA**
[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-wired-light-button-actions.yaml)


**zigbee2mqtt**
[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-wired-light-button-actions.yaml)



### Activate your Scenes or Scripts from your wall switch ###

Toggle lights, cycle scenes or scripts on double press, and adjust brightness with the knob.  Select up to six scenes or scripts  in the blueprint. A simple numeric helper chooses which slot runs next.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-scene-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-scene-control.yaml)



### Control 3 Lights with a single Dimming Switch ###

Solve the common pain of too many wall switches or a confusing app by giving one control point for three lights. Single press toggles the selected light, double press chooses the next light, and rotation brightens or dims only the active light.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-3-light-control-toggle-dimming.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-3-light-control-toggle-dimming.yaml)



### Control Your Speakers and Your Lights with 1 wall dimmer switch ###

Solve the everyday problem of juggling apps or switches by giving one control point for lights and audio. Single press toggles the active target, double press switches to the other target, and rotation adjusts brightness or volume.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-light-and-speaker-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-light-and-speaker-control.yaml)






## Modmote Scene Switch Blueprint ##

A Blueprint to allow easy scene switch configuration for your Candeo Modmote, with press, double press, and hold - for each of the 4 buttons.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-modmote-blueprint-zha.yaml)


**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-modmote-blueprint-zigbee2mqtt.yaml)



## 5-button Scene Switch with rotating dial ##

Bring back effortless wall control for multiple lights from one remote. This blueprint lets the SR5BR pick an active light with buttons 1–4, toggle with the centre, and use the ring to brighten or dim smoothly. It solves the app-only hassle by making the wall control feel fast and reliable again.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-sr5br-ZHA-multi-light-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-sr5br-z2m-multi-light-control.yaml)


Restore natural wall control for a single smart bulb or group. This blueprint lets the SR5BR toggle power, rotate for brightness, and double-press to cycle dial modes—brightness, white temperature, or colour—while scene buttons are optional. It keeps tactile control on the wall so you don’t have to reach for an app.


**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-sr5br-ZHA-smart-bulb-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-sr5br-z2m-smart-bulb-control.yaml)



