# How to play Splatoon 3 before launch on Ryujinx 

## Getting started
First, let's establish what we need to follow this tutorial:
- A decent computer with a GPU that supports the Vulkan API running Windows 10 or 11
- A copy of the Splatoon 3 Splatfest World Premiére (This can either be dumped from a Switch running CFW or obtained easily online. I can't link you to it, use the Google machine)
- Splatoon 3 Splatfest World Premiére Offline Patch Pack (available on the [Gamblitz Discord](https://discord.gg/PsX8qZYCcV) for level 3+ members or on this [mirror](https://matthew5pl.net/files/Release2.zip))
- The latest Switch prod.keys, title.keys and firmware .zip package (Same thing here, you can dump these yourself or find them online)
- [The latest build of Ryujinx LDN](https://github.com/Ryujinx/Ryujinx/wiki/Multiplayer-(LDN-Local-Wireless)-Guide)
- [Radmin VPN](https://www.radmin-vpn.com/)
- A Nintendo Switch Pro Controller (reccomended, but not strictly necessary)

## Ryujinx Setup

Let's begin by opening Ryujinx LDN. If asked to use the Vulkan API instead of OpenGL, select `Yes(Vulkan)`. 

Install the firmware by clicking `Tools > Install Firmware > Install a firmware from XCI or ZIP`. This will open up a file select dialog. Select your firmware .zip package and press `Open`.

Then, [import your keys](https://github.com/Ryujinx/Ryujinx/wiki/Ryujinx-Setup-%26-Configuration-Guide#initial-setup---placement-of-prodkeys) as well as [Splatoon 3](https://github.com/Ryujinx/Ryujinx/wiki/Ryujinx-Setup-%26-Configuration-Guide#adding-your-games-to-ryujinx).

Finally, open `Options > Settings > System` and enable `Ignore Missing Services`.

## Patching the game

Once Splatoon 3 shows up in the main menu, right click it and select `Open Atmosphere Mods Directory`.

This will open up an Explorer Window. You should see this kind of folder structure in the top bar:
`.../Ryujinx/sdcard/atmoshpere/contents/0100ba0018500000`

Navigate to the `atmosphere` folder by clicking on its name in the top bar, then open a separate Explorer Window and open the `Release2.zip` file.

Inside you will find another `atmosphere` folder. Simply open that folder and drag its contents inside of the Explorer Window from earlier.

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

As `Input Device`, select `Nintendo Switch Pro Controller`. As controller type, select `Pro Controller`. Finally, under `Profile`, leave it as `Default` and select `Load`. Finally press `Save`.

## LAN Play Setup

Open Ryujinx again, and select `Options > Settings > Multiplayer > LAN Mode > Network Interface`. This will open a dropdown menu. Everytime you boot the game, make sure this is set to `Radmin VPN` and that `System > Enable Guest Internet Access` is off.

Open Splatoon 3 by double clicking it. Go through the tutorial and once you're in the plaza, open `Options > Settings > System > Enable Guest Internet Access`. This option needs to be off when the game is loading, and on when you reach the plaza everytime you play. If you leave this option on all the time, the game will try loading the news and get stuck on the loading screen.

Once you're in the plaza, visit the Lobby. Once it is done loading, hold `ZL` + `ZR` + `Left Stick` for 5 seconds to enter LAN Mode. If you get kicked out from LAN mode after it tries to load, it means that `Options > Settings > System > Enable Guest Internet Access` is off. Finally, you can press `L` and create a private room to play with your friends. Salmon Run DOES NOT WORK as the Splatfest World Premiére is missing the files necessary for it to work. Otherwise, you can play all Ranked modes and Turf War like normal.
