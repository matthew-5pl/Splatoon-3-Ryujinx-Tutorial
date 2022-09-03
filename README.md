# How to play Splatoon 3 before launch on Ryujinx 

## Splatoon 3 Matchmaking Discord
Join [this](https://discord.gg/d8TBPEKYwZ) server to find people to play Splatoon 3 with!

## Getting started
First, let's establish what we need to follow this tutorial:
- A decent computer with a GPU that supports the Vulkan API running Windows 10 or 11
- A copy of the Splatoon 3 Splatfest World Premiére (This can either be dumped from a Switch running CFW or obtained easily online. I can't link you to it, use the Google machine)
- Splatoon 3 Splatfest World Premiére Offline Patch Pack (available on the [Gamblitz Discord](https://discord.gg/PsX8qZYCcV) for level 3+ members or on this [mirror](https://matthew5pl.net/files/Release2.zip))
- [News Skip Patch](https://cdn.discordapp.com/attachments/1014868735242272841/1015552740874792960/Offline_boot.zip) by `Shadów#1337` ([here](https://twitter.com/shadowninja108) on Twitter)
- The latest Switch prod.keys, title.keys and firmware .zip package (Same thing here, you can dump these yourself or find them online)
- [The latest build of Ryujinx LDN](https://github.com/Ryujinx/Ryujinx/wiki/Multiplayer-(LDN-Local-Wireless)-Guide)
- [Radmin VPN](https://www.radmin-vpn.com/)
- A Nintendo Switch Pro Controller (reccomended, but not strictly necessary)

## Ryujinx Setup

Let's begin by opening Ryujinx LDN. If asked to use the Vulkan API instead of OpenGL, select `Yes(Vulkan)`. 

First, [import your keys](https://github.com/Ryujinx/Ryujinx/wiki/Ryujinx-Setup-%26-Configuration-Guide#initial-setup---placement-of-prodkeys).

Then, install the firmware by clicking `Tools > Install Firmware > Install a firmware from XCI or ZIP`. This will open up a file select dialog. Select your firmware .zip package and press `Open`.

Next, import [Splatoon 3](https://github.com/Ryujinx/Ryujinx/wiki/Ryujinx-Setup-%26-Configuration-Guide#adding-your-games-to-ryujinx).

Enable `Options > System > Enable Guest Internet Access`.

Finally, open `Options > Settings > System` and enable `Ignore Missing Services`.

## Patching the game

Once Splatoon 3 shows up in the main menu, right click it and select `Open Atmosphere Mods Directory`.

This will open up an Explorer Window. You should see this kind of folder structure in the top bar:
`.../Ryujinx/sdcard/atmoshpere/contents/0100ba0018500000`

Navigate to the `atmosphere` folder by clicking on its name in the top bar, then open a separate Explorer Window and open the `Release2.zip` file.

Inside you will find another `atmosphere` folder. Simply open that folder and drag its contents inside of the Explorer Window from earlier.

Then, open the `Offline_boot.zip` and navigate back to `.../Ryujinx/sdcard/atmoshpere/contents/0100ba0018500000`. 

Drag the `exefs` folder from the zip to the `0100ba0018500000` folder.

Your game should now be successfully patched. You can close all Explorer Windows.

We can close Ryujinx for now.

## Setting up Radmin VPN

Once you have installed Radmin VPN, you have two options:

- Hosting a Network for you and your friends
- Joining an existing network

If one of your friends already set a network up, select `Network > Join Network +` and ask them to provide you their Radmin VPN Network Username & Password. Input them in the respective text fields and select `Join`.

Otherwise, create a network using `Network > Create Network` and store your credentials in a text file for sharing.

## (Optional) Pro Controller Setup

Plug your Nintendo Switch Pro Controller into a free USB port in your computer using a USB Type-C to USB Data cable.

In Ryujinx, open `Options > Settings > Input > Player 1 > Configure`.

As `Input Device`, select `Nintendo Switch Pro Controller`. As controller type, select `Pro Controller`. Then, under `Profile`, leave it as `Default` and select `Load`. Finally press `Save`.

## LAN Play Setup

Open Ryujinx again, and select `Options > Settings > Multiplayer > LAN Mode > Network Interface`. This will open a dropdown menu. Everytime you boot the game, make sure this is set to `Radmin VPN` and that `System > Enable Guest Internet Access` is on.

Open Splatoon 3 by double clicking it. Once you're in the plaza, visit the Lobby. Once it is done loading, hold `ZL` + `ZR` + `Left Stick` for 5 seconds to enter LAN Mode.

If you get kicked out from LAN mode after it tries to load, it means that `Options > Settings > System > Enable Guest Internet Access` is off. Finally, you can press `L` and create a private room to play with your friends. Salmon Run DOES NOT WORK as the Splatfest World Premiére is missing the files necessary for it to work. Otherwise, you can play all Ranked modes and Turf War like normal.

## Quirks

Here is a list of some quirks reported by Ryujinx users playing Splatoon 3:
### Rainmaker

If you try playing Rainmaker Mode, you won't be able to end the game with a knockout as all checkpoints after the first one don't work.

### AMD Issues
Some users with AMD GPUs have been having issues with artifacting, going from mild to severe:
  
<img alt="Severe artifacting issues on an RX 580" style="width: 400px; height: 223px;" src="https://raw.githubusercontent.com/matthew-5pl/Splatoon-3-Ryujinx-Tutorial/main/amd.png">

Here is a list of known affected maps:

<img src="https://raw.githubusercontent.com/matthew-5pl/Splatoon-3-Ryujinx-Tutorial/main/avoid2.jpg">
    
### Softlocks

Once you enter the LAN Play lobby, pressing `+` to switch weapons or `A` to interact with the Gacha machine or the food stand will softlock the game. If this happens you must restart the game.

### Shaders loading

While playing an online match, if one of the users attempts to load a shader they've never loaded (like opening the minimap) their game will stutter until it's done loading and the message `The connection is unstable.` will appear on everyone else's screen.
