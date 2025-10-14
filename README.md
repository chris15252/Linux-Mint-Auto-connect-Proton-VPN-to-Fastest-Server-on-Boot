# Auto-start & connect Proton VPN on boot
These are step by step instructions on setting up Proton VPN in Linx Mint [^1] to automatically start on boot, minimize to the system tray, and automatically connect to the fastest available server without needing user input. This will help ensure that all internet traffic is secured via VPN by mitigating the chances of forgetting to activate the VPN service when logging in. 

> [!NOTE]
> It is assumed that the user is on [Linux Mint Cinnamon Edition](https://linuxmint.com/edition.php?id=322) and has already installed the [Proton VPN app](https://protonvpn.com/support/linux-vpn-setup) prior to following these instructions. If not, please follow the installation structions of each and return here after those have been installed.  

## Add to Startup Application list

First we will add Proton VPN to the list of applications that start immediately upon boot.

1. First, go to the Startup Applications menu: **Start > Preferences > Startup Applications**
   -  ![Start Menu](/Images/Screenshot%20from%202025-10-14%2010-31-13.png)
   <br/>

2. In the Startup Applications window click the **+** button and select Choose application.
   -  ![Startup Applications](/Images/Screenshot%20from%202025-10-14%2010-46-33.png)
  <br/>

3. Search for Proton VPN, select it and click **Add Application**.  <br/><br/>
   -  ![Application Search](/Images/Screenshot%20from%202025-10-14%2010-58-22.png)

## Minimize to System Tray on boot

Next, we want to ensure that when Proton VPN starts it immediately minimizes to the system tray on boot. 

4. Click the pencil icon, which will bring up the **Edit Startup Program** menu, and append the following command to the **Command** box: 
```bash
--start-minimized

# The full command should look like this

protonvpn-app --start-minimized
```
   -  ![Start Minimized](/Images/Screenshot%20from%202025-10-14%2011-00-51.png)

## Auto-connect to fastest server

Lastly we want our VPN to connect automatically, without without needing user input.
> [!NOTE]
> The setting chosen for this example will connect to the fastest available server, typically in the same country as the user. However, there are other manual options available that may be entered instead. For example, to connect to a server in a specific country, input the country ISO code (e.g.: US for United States) and Proton VPN will automatically connect to that country. The user may also to specify which server the VPN connects to by entering the server name (e.g.: NL#42).

5. Now open the Proton VPN app, click the down arrow in the top left, and select **Settings**.
   -  ![Proton App](/Images/Screenshot%20from%202025-10-14%2011-03-43.png)

6. Scroll towards the bottom and look for **Auto connect** under the **General** heading and enter:
```bash
FASTEST
```
   -  ![Auto Connect Fastest](/Images/Screenshot%20from%202025-10-14%2011-35-37.png)

7. Close the window to save the setting.

## Test it out
After completing the above steps, you should be able to log out or reboot and Proton will automatically start after logging in. After starting it will establish a VPN connection, according to your connection preferences, and then minimize to the sytem tray, all without user input. 

[^1]: These instructions are based on Linux Mint 22.2 'Zara' Cinnamon Edition. They have not been tested in other Linux distros, so please follow them at your own discretion. 
