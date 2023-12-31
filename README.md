# Raspberry Pi Pi-Hole Setup

## Banishing Banners: Conquering Ads with Raspberry Pi Pi-Hole

Tired of intrusive ads marring your online experience? Say goodbye to pop-ups and banners with your very own **Raspberry Pi Pi-Hole**, a free and open-source ad blocker that transforms your Raspberry Pi into a network-wide shield against unwanted advertisements. This tutorial will guide you through the **step-by-step process** of setting up Pi-Hole on your Raspberry Pi, paving the way for a cleaner and more enjoyable browsing journey.

## Prepping for Battle:

Before we embark on our ad-slaying quest, gather your arsenal:

* **Raspberry Pi:** Any model will do, though a Pi 3B+ or later offers optimal performance.
* **MicroSD card:** At least 8GB for a basic setup.
* **Raspberry Pi power supply:** Ensures your Pi stays energized.
* **HDMI cable and monitor (optional):** For initial configuration and visual feedback.
* **Ethernet cable:** Connects your Pi to your network.
* **Internet connection:** A vital gateway to the digital battlefield.

## Software Squadron:

* **Raspberry Pi OS Lite:** A streamlined OS for efficient Pi-Hole operation. Download the latest version.
* **Pi-hole:** Your trusty ad-blocking champion. Get it from the [official website](https://www.tomshardware.com/how-to/set-up-pi-hole-raspberry-pi).

![Image credit tom's hardware](https://cdn.mos.cms.futurecdn.net/m5rpwSos3caMMrrbbsWJ3Z-970-80.gif)
![Image credit tom's hardware](https://cdn.mos.cms.futurecdn.net/tGejDgprEhg6Wyj8uoe3aZ-970-80.png)

## Step 1: Flashing Forward (Preparing the Raspberry Pi):

1. **Flashing Frenzy:** Use a tool like Etcher to write the Raspberry Pi OS image onto your microSD card. [Guide here](https://raspberrytips.com/raspberry-pi-imager-guide/)
2. **Boot Camp:** Insert the microSD card into your Pi, connect the power supply, and (if using) the HDMI cable and monitor. Power on your Pi!
3. **Configuration Cavalry:** Follow the on-screen instructions to set up your Raspberry Pi, including username/password creation, Wi-Fi configuration (if not using Ethernet), and system updates.
# Installing Pi-hole Over SSH

SSH, a secure connection to your Raspberry Pi, is the best way to install and set up Pi-hole. We can use an SSH client to connect. For Windows, this is PuTTY, and Mac, Linux users can directly connect via the terminal. With SSH, we can install software and administrate the Raspberry Pi as if we were sitting in front of it.

1. **For Windows users:**
   - Download and install [PuTTY](https://www.putty.org/).
   
2. **For Linux and Mac users:**
   - Open a terminal.

3. **Via PuTTY:**
   - Enter the hostname as `raspberrypi.local` (on some networks, this is just `raspberrypi` without the .local) and then click Open.

   ![PuTTY](https://cdn.mos.cms.futurecdn.net/EFqhRqYKir7CbnfzNsX7Ub-970-80.png)

4. Enter your username and password when prompted. Note that these are not printed to the screen for security purposes.

![putty terminal](https://s3.amazonaws.com/libapps/accounts/10946/images/2016-08-18-190939_657x399_scrot-hl.png)

## Step 2: Installing the Pi-Hole:

1. **Terminal Territory:** Open a terminal window on your Raspberry Pi desktop.
2. **Update Arsenal:** Run `sudo apt update` to ensure you have the latest software packages.
3. **Summon the Pi-Hole:** Enter `curl -s https://install.pi-hole/ | bash` and follow the installation wizard. Choose your upstream DNS providers (e.g., Google, Cloudflare) and desired adlists to block.
4 ** Choose eth0 as the interface to use with Pi-hole. Press Tab to move the red highlight to Ok and then press Enter. This is our Gigabit Ethernet port which will provide the best possible connection. 

## Step 3: Routing the Way to Ad-Free Bliss:

1. **Scouting the Enemy:** In the terminal, run `ip addr` to find your Pi-hole's IP address. Look for it under the `eth0` interface (or `wlan0` if using Wi-Fi).
2. **Router Recon:** Access your router's admin interface via a web browser (usually at 192.168.1.1). Enter your router's username and password to log in.
3. **DNS Demise:** Navigate to the DHCP or DNS settings section. Set the primary DNS server to your Pi-hole's IP address. You may also need to set a secondary DNS server.
4. **Victory Reboot:** Save your changes and reboot your router. Wait for it to come back online, and your devices should now be using Pi-hole for DNS lookups, effectively blocking ads!

## Step 4: Conquering from the Command Center (Optional):

1. **Web Interface Wisdom:** Open a web browser on any device connected to your network and type `http://pi.hole/` in the address bar.
2. **Login Legend:** Use the username and password you set during Pi-hole installation.
3. **Stats and Strategies:** Explore the Pi-hole interface to see blocked ad statistics, query domains, and manage your adlists. Customize your ad-blocking experience to your liking!


## Behold, a Banner-Free Future!

You've successfully set up Pi-hole on your Raspberry Pi, reclaiming your browsing freedom from the clutches of intrusive ads. Enjoy a cleaner, faster online experience, and relish the satisfaction of vanquishing those pesky pop-ups and banners. Remember to keep your Raspberry Pi and Pi-hole software updated for optimal performance and security. Now, go forth and conquer the digital wilderness, ad-free and triumphant!

## Bonus Tips:

* Manually configure individual devices to use Pi-hole for DNS by entering its IP address as the preferred DNS server in their network settings.
* Explore Pi-hole's advanced features and customization options in the web interface to tailor your ad-blocking experience.
* Consider adding a heatsink to your Raspberry Pi for improved stability, especially if you plan to run it for extended periods.
