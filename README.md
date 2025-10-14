# Auto-start Proton VPN on boot and auto-connect to fastest server
**These are step by step instructions on setting up Proton VPN in Linx Mint [^1] to automatically start on boot, minimize to the system tray, and automatically connect to the fastest available server without needing user input.**

>  It is assumed that the user has already installed the [Proton VPN app](https://protonvpn.com/support/linux-vpn-setup) prior to following these instructions.

First, go to the Startup Applications menu: 

**Start > Preferences > Startup Applications**

![Start Menu](https://github.com/chris15252/Linux-Mint-Auto-connect-Proton-VPN-to-Fastest-Server-on-Boot/blob/main/Images/Screenshot%20from%202025-10-14%2010-31-13.png "Start Menu")

In the Startup Applications window click the **+** button and select Choose application.

![Startup Applications](https://github.com/chris15252/Linux-Mint-Auto-connect-Proton-VPN-to-Fastest-Server-on-Boot/blob/main/Images/Screenshot%20from%202025-10-14%2010-46-33.png)

Search for Proton VPN, select it and click **Add Application**.

![Application Search](https://github.com/chris15252/Linux-Mint-Auto-connect-Proton-VPN-to-Fastest-Server-on-Boot/blob/main/Images/Screenshot%20from%202025-10-14%2010-58-22.png)

Next, click the pencil icon, which will bring up the **Edit Startup Program** menu. Append the following command to the **Command** box:

```bash
--start-minimized

# The full command should look like this

protonvpn-app --start-minimized
```

![Start Minimized](https://github.com/chris15252/Linux-Mint-Auto-connect-Proton-VPN-to-Fastest-Server-on-Boot/blob/main/Images/Screenshot%20from%202025-10-14%2011-00-51.png)

This will force Proton VPN to start in the System Tray rather than opening the GUI window at boot. Now open the Proton VPN app, click the down arrow in the top left, and select **Settings**.

![Proton App](https://github.com/chris15252/Linux-Mint-Auto-connect-Proton-VPN-to-Fastest-Server-on-Boot/blob/main/Images/Screenshot%20from%202025-10-14%2011-03-43.png)

Scroll towards the bottom and look for **Auto connect** under the **General** heading. In the **Auto connect** input box enter:

```bash
FASTEST
```

![Auto Connect Fastest](https://github.com/chris15252/Linux-Mint-Auto-connect-Proton-VPN-to-Fastest-Server-on-Boot/blob/main/Images/Screenshot%20from%202025-10-14%2011-35-37.png)

Close the window to save the setting. This option will quick connect to the fastest available server.

[^1]: The target OS when writing these instructions was Linux Mint 22.2 'Zara' Cinnamon Edition. These instructions are untested in other Linux distros, so follow at your own discretion. 
