# Home Assistant Blueprints for Candeo devices #

## Devices ##

1. [RD1-Pro](#rd1-pro-c-zb-rd1p-decoupled-dimming-switch)
2. [Modmote Scene Switches (CMM-1)](#modmote-scene-switch-blueprint)
3. [5 Button Scene Switch with Rotating Dial (C-ZB-SR5BR)](#5-button-scene-switch-with-rotating-dial)



## RD1-Pro (C-ZB-RD1P) Decoupled Dimming Switch ##

**13 Blueprints for the RD1-Pro (C-ZB-RD1P) Decoupled Dimming Switch**

The RD1-Pro can be used with Home Assistant in several different ways. The blueprints below are grouped by purpose so you can choose between flexible Home Assistant control, additional functions while remaining in DIM mode, or direct Zigbee control.

### Important: RD1-Pro Firmware v2 ###

Some of the newer blueprints require **RD1-Pro firmware v2**:

- **RD1-Pro Zigbee firmware v2.0.0 or later**
- **RD1-Pro MCU firmware v2.0.0 or later**

Firmware v2 adds features including **Extra Button Commands** and **direct Zigbee binding**. Blueprints that require firmware v2 are clearly marked below.

### Important: Direct Zigbee Binding ###

Direct binding allows the RD1-Pro to send on/off and dimming commands directly to another compatible Zigbee light or Zigbee group instead of routing every command through Home Assistant.

For direct binding, the RD1-Pro and the target must be on the **same Zigbee network**. For example, an RD1-Pro paired to ZHA can directly bind to compatible lights or groups on that same ZHA network. An RD1-Pro paired to zigbee2mqtt can directly bind to compatible targets on that same zigbee2mqtt network.

A Philips Hue bulb that remains paired to a separate Hue Bridge cannot be directly bound to an RD1-Pro on ZHA or zigbee2mqtt. It would need to be paired directly to the same Zigbee network as the RD1-Pro.

For ZHA users, the direct-binding blueprints require **ZHA Toolkit**.


<a id="rd1-pro-blueprint-navigation"></a>
### RD1-Pro Blueprint Navigation ###

**Home Assistant Control**

1. [Smart Bulb Control via Home Assistant](#rd1p-smart-bulb-home-assistant)
2. [Wired Light + Button Actions](#rd1p-wired-light-button-actions)
3. [Scene & Script Control](#rd1p-scene-script-control)
4. [3-Light Selector & Dimming Control](#rd1p-3-light-selector)
5. [Light + Speaker Control](#rd1p-light-speaker-control)

**Firmware v2 - DIM Mode + Extra Functions**

6. [DIM Mode - Extra Button Actions](#rd1p-dim-extra-button-actions)
7. [DIM Mode - Secondary Light Control with Hold-to-Dim Cycle](#rd1p-dim-secondary-light)
8. [DIM Mode - Blinds / Curtains](#rd1p-dim-blinds-curtains)

**Firmware v2 - Direct Zigbee Binding**

9. [Bind to Light or Zigbee Group](#rd1p-bind-light-group)
10. [Bound Light + Extra Actions](#rd1p-bound-light-extra-actions)
11. [Direct-Binding Light / Group Selector](#rd1p-direct-binding-selector)

**Direct-Binding Management**

12. [Unbind from Light or Zigbee Group](#rd1p-unbind-light-group)
13. [Clear / Reset Bindings](#rd1p-clear-reset-bindings)



### Home Assistant Control ###

These blueprints send RD1-Pro button and rotary events to Home Assistant, which then controls the selected device. This is the most flexible approach because the target does not need to be on the same Zigbee network - and does not even have to be a Zigbee device.

<a id="rd1p-smart-bulb-home-assistant"></a>
#### Smart Bulb Control via Home Assistant ####

Bring back natural wall control for your smart bulbs without cutting power. This blueprint lets the RD1-Pro knob toggle and dim a smart bulb or light group, as well as adjust white temperature and colour. It works through Home Assistant, so the target can be a Zigbee light, a Wi-Fi bulb, a Hue bulb connected through a Hue Bridge, or another compatible Home Assistant light entity.

**Related alternative:** [Bind to Light or Zigbee Group](#rd1p-bind-light-group) provides similar basic on/off and dimming control, but sends those commands directly over Zigbee. Direct binding requires **RD1-Pro firmware v2**, a compatible Zigbee target, and both devices to be on the **same Zigbee network**.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-smart-bulb-colour-light-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-smart-bulb-colour-light-control.yaml)


<a id="rd1p-wired-light-button-actions"></a>
#### Wired Light + Button Actions ####

Control your wired light circuit while also making double press, hold and release available to Home Assistant. This blueprint uses the RD1-Pro in DPM mode so the switch can operate its wired dimmable load while Home Assistant responds to the additional button events.

**Example use case:** Use the RD1-Pro normally for the main ceiling lights, while double press activates lamps or launches an evening scene.

**Related alternative:** With **RD1-Pro firmware v2**, [DIM Mode - Extra Button Actions](#rd1p-dim-extra-button-actions) allows the RD1-Pro to remain in normal DIM mode while exposing the additional button commands.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-wired-light-button-actions.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-wired-light-button-actions.yaml)


<a id="rd1p-scene-script-control"></a>
#### Scene & Script Control ####

Toggle lights, cycle scenes or scripts on double press, and adjust brightness with the knob. Select up to six Home Assistant scenes or scripts in the blueprint, with a simple numeric helper choosing which slot runs next.

**Example use case:** Cycle a living room through **Bright -> Relax -> Movie -> Night** without opening the Home Assistant app.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-scene-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-scene-control.yaml)


<a id="rd1p-3-light-selector"></a>
#### 3-Light Selector & Dimming Control ####

Give one RD1-Pro control of three Home Assistant lights. Single press toggles the selected light, double press chooses the next light, and rotation brightens or dims only the active light.

**Example use case:** Switch between **Ceiling Lights -> Pendants -> Cabinet Lights** from one wall control.

**Related alternative:** [Direct-Binding Light / Group Selector](#rd1p-direct-binding-selector) offers a similar user experience but changes the RD1-Pro's actual Zigbee binding. Choose this 3-Light Selector when the targets are Home Assistant entities - including Zigbee, Wi-Fi or other smart lights - and flexibility is more important than direct Zigbee communication. Choose the Direct-Binding Selector when the targets are compatible Zigbee lights or groups on the **same Zigbee network** as the RD1-Pro and direct Zigbee control is preferred.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-3-light-control-toggle-dimming.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-3-light-control-toggle-dimming.yaml)


<a id="rd1p-light-speaker-control"></a>
#### Light + Speaker Control ####

Use one wall dimmer for both lighting and audio. Single press toggles the active target, double press switches between the light and speaker, and rotation adjusts either brightness or volume.

**Example use case:** Use the knob normally to dim your living-room lights, then double press and rotate the same knob to control your Sonos volume.

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1P-light-and-speaker-control.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1P-light-and-speaker-control.yaml)




### Firmware v2 - DIM Mode + Extra Functions ###

These blueprints use the **Extra Button Commands** introduced with **RD1-Pro firmware v2**. The RD1-Pro remains in normal DIM mode, so single press and rotation continue to operate the connected wired light normally while Home Assistant can also respond to double press, hold and release.

<a id="rd1p-dim-extra-button-actions"></a>
#### DIM Mode - Extra Button Actions ####

Add your own Home Assistant actions to double press, hold and release while the RD1-Pro continues operating its wired light normally in DIM mode.

**Example use case:** Double press activates an evening scene, while hold turns off all of the downstairs lights.

This is the general-purpose DIM mode blueprint. The Secondary Light and Blinds / Curtains blueprints below provide ready-made behaviour for specific uses.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-DIM-extra-button-actions.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-DIM-extra-button-actions.yaml)


<a id="rd1p-dim-secondary-light"></a>
#### DIM Mode - Secondary Light Control with Hold-to-Dim Cycle ####

Keep normal control of the RD1-Pro's wired circuit while using the Extra Button Commands to control a second Home Assistant light. Holding the knob continuously cycles the secondary light's brightness **up -> down -> up** until the knob is released.

**Example use case:** The RD1-Pro controls the bedroom ceiling lights normally, while its extra commands toggle and smoothly dim a pair of bedside lamps.

The secondary target is a Home Assistant light entity and does not need to be directly Zigbee-bound to the RD1-Pro.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-DIM-secondary-light-hold-to-dim-cycle.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-DIM-secondary-light-hold-to-dim-cycle.yaml)


<a id="rd1p-dim-blinds-curtains"></a>
#### DIM Mode - Blinds / Curtains ####

Keep normal wired-light control while using the RD1-Pro's Extra Button Commands to operate a Home Assistant blind or curtain entity.

**Example use case:** The RD1-Pro controls the bedroom ceiling light normally while its additional button commands open, close or stop the bedroom curtains.

This can also be built manually with the general Extra Button Actions blueprint, but this version provides the cover-specific behaviour ready to configure.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-DIM-blinds-curtains.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-DIM-blinds-curtains.yaml)




### Firmware v2 - Direct Zigbee Binding ###

Direct binding sends normal on/off and dimming commands **directly from the RD1-Pro to a compatible Zigbee light or Zigbee group** rather than asking Home Assistant to process every command.

All direct-binding blueprints require **RD1-Pro firmware v2**, and the RD1-Pro and target must be on the **same Zigbee network**. ZHA versions also require **ZHA Toolkit**.

<a id="rd1p-bind-light-group"></a>
#### Bind to Light or Zigbee Group ####

Create a direct Zigbee binding for On/Off and Level Control between the RD1-Pro and a compatible Zigbee light or Zigbee group.

**Example use case:** An RD1-Pro paired to zigbee2mqtt directly controls a Zigbee group containing six kitchen downlights on the same zigbee2mqtt network.

This is the direct-Zigbee alternative to [Smart Bulb Control via Home Assistant](#rd1p-smart-bulb-home-assistant). Use the Home Assistant blueprint when you need colour, colour-temperature, Wi-Fi lights, a separate Hue Bridge or maximum flexibility. Use direct binding when the compatible Zigbee target is on the same network and you primarily want fast, direct on/off and dimming.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-bind-lights-or-groups.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-bind-lights-or-groups.yaml)


<a id="rd1p-bound-light-extra-actions"></a>
#### Bound Light + Extra Actions ####

Combine direct Zigbee lighting with Home Assistant automation. Single press and rotation control the bound Zigbee light or group directly, while double press, hold and release remain available for Home Assistant actions.

**Example use case:** Single press and rotation directly control a kitchen Zigbee lighting group, double press activates an evening scene, and hold closes the blinds.

The directly controlled light or group must be on the **same Zigbee network as the RD1-Pro**.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-bound-light-extra-actions.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-bound-light-extra-actions.yaml)


<a id="rd1p-direct-binding-selector"></a>
#### Direct-Binding Light / Group Selector ####

Use one RD1-Pro to directly control several different Zigbee targets. Home Assistant keeps a list of possible lights or groups, and double press changes which target the RD1-Pro is directly bound to. Single press and rotation then control that selected target directly over Zigbee.

**Example use case:** Cycle direct control between **Ceiling Lights -> Lamps -> Whole Room -> Ceiling Lights**.

All selectable targets must be compatible Zigbee lights or groups on the **same Zigbee network as the RD1-Pro**.

This is the direct-Zigbee alternative to the [3-Light Selector & Dimming Control](#rd1p-3-light-selector).

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-direct-binding-light-group-selector.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-direct-binding-light-group-selector.yaml)




### Direct-Binding Management ###

These are configuration and maintenance blueprints for direct Zigbee bindings rather than everyday control automations. They require **RD1-Pro firmware v2**, and ZHA versions require **ZHA Toolkit**.

<a id="rd1p-unbind-light-group"></a>
#### Unbind from Light or Zigbee Group ####

Remove the RD1-Pro's direct On/Off and Level Control binding from one specified Zigbee target without intentionally removing unrelated direct bindings.

**Example use case:** Your RD1-Pro currently controls **Kitchen Lights**, but you now want to assign it to **Dining Lights** instead. Unbind Kitchen Lights before creating the new binding.

The RD1-Pro and target must be on the **same Zigbee network**.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-unbind-lights-or-groups.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-unbind-lights-or-groups.yaml)


<a id="rd1p-clear-reset-bindings"></a>
#### Clear / Reset Bindings ####

Return the RD1-Pro's customer-created direct-binding configuration to a clean state so you can start again. The ZHA and zigbee2mqtt versions use platform-appropriate methods designed to preserve or restore the bindings required for normal coordinator operation.

**Example use case:** You have experimented with several different lights and Zigbee groups and want to rebuild the direct-binding configuration from a clean state.

**Requires RD1-Pro firmware v2.**

**ZHA**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zha-RD1Pv2-clear-reset-bindings.yaml)

**zigbee2mqtt**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/candeosmart/homeassistant-blueprints/blob/main/candeo-blueprint-zigbee2mqtt-RD1Pv2-clear-reset-bindings.yaml)



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



