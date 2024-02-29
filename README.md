Additional stateful blinds icons for use by the [**_RFXCOM RFXtrx Stateful Blinds_**](https://github.com/RJArmitage/rfxtrx-stateful-blinds) custom integration.

# What does it do?

The additional icons allow the **_RFXtrx Stateful Blinds_** integration to show the tilt state of Somfy venetian blinds and Louvolite vertical blinds.

The Stateful Blinds integration allows Home Assistant to track whether or not the blinds are tilted and by how much. The Stateful Blinds Icons package provides icons that allow the integration to show the state of tilt as well as whether the blind is classed as "open" or "closed":

<img src="https://raw.githubusercontent.com/RJArmitage/rfxtrx-stateful-blinds-icons/main/dist/icons/venetian/active/20.svg" alt="MarineGEO circle logo" style="height: 75px; width:75px;"/> <img src="https://raw.githubusercontent.com/RJArmitage/rfxtrx-stateful-blinds-icons/main/dist/icons/venetian/inactive/50.svg" alt="MarineGEO circle logo" style="height: 75px; width:75px;"/> <img src="https://raw.githubusercontent.com/RJArmitage/rfxtrx-stateful-blinds-icons/main/dist/icons/vertical/active/25.svg" alt="MarineGEO circle logo" style="height: 75px; width:75px;"/> <img src="https://raw.githubusercontent.com/RJArmitage/rfxtrx-stateful-blinds-icons/main/dist/icons/vertical/inactive/00.svg" alt="MarineGEO circle logo" style="height: 75px; width:75px;"/>

# Why does it exist? Do I need it?

You possibly don't - it's intended to satisfy a specific requirement. Maybe you share it with me...

I have a bunch of venetian blinds which use Somfy motors. Now for me the whole point of venetian blinds is to provide more control over the light in my home while maintaining privacy as best I can. I spent a lot of money on the motors and am unhappy with the basic features I got in Home Assistant. I want some specific capabilities that the base Home Assistant RFXtrx cover support doesn’t give me. Note that this is an opinionated list. These are the facilities that _I_ expect from the way I want to use venetian blinds:

- I want to fully get the benefit of the tilt functions of my blinds. I want to be able to tilt the blind to any position that the blind supports. I have installed venetian blinds to control the light in my house and my privacy. Simply being able to be open or closed doesn't cut it.

- I want to get full scripting support. I should be able to tell the blind to tilt to 70% say and have the blind "know" that it is currently tilted to 30% so needs to step 7 positions to get to 70% tilted. This also makes support via Alexa better as I can tell the blind to tilt to 80% or whatever.

- The concept of "opening" and "closing" the blinds should relate to tilting the blind and not lifting. To me an open venetian blind is one that is dropped and then tilted to open - not one that is lifted. A closed blind is both dropped and fully tilted closed.

- Privacy is key. I want to be certain that the blinds will only attempt to lift if they are explicitly told to. In particular when using Alexa integration, if Alexa is told to "open" the blind then it should do this by tilting the blind to open and **not** by lifting the blind.

- I want to be able to control my blinds using Somfy groups as well as individually. Somfy motors can assign a single channel on their controller to more than one blind. This means that to control all those blinds only a single instruction is sent. Now, it is possible to do something similar in Home Assistant by creating a cover group. But that's missing the point of the Somfy function. It would mean that each operation would be sent separately to each blind in the group. That's irritating to me as all the blinds start and stop moving separately with a sort of ripple effect. I have 5 blinds in a bay window and this looks untidy! I want to use the function I paid for.

- I want the blind icon in Home Assistant to show the state of the blind. If it's tilted open then that should be obvious and different from it being tilted closed. If the blind is lifted then that should be very obvious.

- I want support for Louvolite Vogue vertical blinds which RFXtrx doesn't normally support.

So, if you have one or more of those requirements then maybe this component will be useful for you. If not then you should continue with the existing built-in Home Assistant RFXtrx integration.

# Which blinds are supported

The Stateful Blinds implementation only supports three types of blinds. It is fully compatible with everying else that RFXtrx supports and in that case just uses the existing RFXtrx functionality:

- **_Venetian blinds_** using **_Somfy_** battery and mains-powered RTS motors such as **Sonesse** and **Lift & Tilt** motors.

- **_Vertical blinds_** using **_Louvolite Vogue_** battery powered motors. Note that this requires RFXtrx firmware 1044 or better.

- **_Roller blinds_** using **_Somfy_** battery and mains-powered RTS motors.

Why only those blinds? Simply because those are the ones I have so those are the ones I can test against. If you don't have the same devices as me then this likely isn't the component for you as you likely won't see any benefit.

# How do I get it?

If you've read to here and still want to try it then installation is best done through HACS.

## HACS (Recommended)

This is the recommended way to install rfxtrx-stateful-blinds-icons. To install:

- Open HACS (installation instructions are [here](https://hacs.xyz/docs/installation/installation/))
- Go to "Frontend" section
- Click the button with an "+" icon
- Search for "RFXCOM RFXtrx Stateful Blind Icons" and install it

However to make use of the icons you'll need to install the **_RFXCOM RFXtrx Stateful Blinds_** custom integration. As this replaces the standard **_RFXCOM RFXtrx_** integration it is not available in the default HACS Community Store.

Check [**_RFXCOM RFXtrx Stateful Blinds_**](https://github.com/RJArmitage/rfxtrx-stateful-blinds) for details of how to install.
