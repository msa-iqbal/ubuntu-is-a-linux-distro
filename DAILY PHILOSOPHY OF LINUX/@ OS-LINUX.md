# 🗁 Install & Conf. Linux Packages
---
### 🗳 GP Modem

<http://192.168.0.1/index.html#login>

**⎙ Install Grameen-Phone Modem (GP Modem):**

- Step 1: Copy `PCL_BengalGP.tar.gz` and paste ubuntu’s "Home" location
- Step 2: Extract `PCL_BengalGP.tar.gz` and open `PCL_BengalGP` folder
- Step 3: Open terminal and type: `sudo ./install.sh` then press `ENTER`.

### 🗳 Access Share Folder @ Windows10-OS

```plaintext
COMPUTER  : Jasmin-PC
--------- : -------------------
PATH      : smb://192.168.1.103
USER-NAME : jas
PASSWORD  : z
```

**⎙ Access Share Folder from "Windows 10 OS"**

Install "Samba"

```bash
sudo apt install samba
```

Goto Searchbar and type Windows-PC's IP as like:

```plaintext
smb://192.168.1.102
```

### 🗳Github - SSH

```plaintext
Pass: 256858
```

### 🗳 When didn't Support NTFS Format

When didn't Support NTFS Format (USB Drive / Pendrive)
Ref: <https://www.youtube.com/watch?v=hDq96zim1V4>

```bash
sudo fdisk -l
sudo apt-get install nfs-common
sudo apt-get install cifs-utils
sudo ntfsfix -d /dev/sdf1
```

### 🗳 Waydroid (Run Android Apps)

Video Tutorial: <https://youtu.be/gcTbDSvaXmY>
Guide: <https://docs.waydro.id/usage/install-on-desktops>

Install Waydroid:

```bash
sudo apt install curl ca-certificates -y
```

```bash
curl -s https://repo.waydro.id | sudo bash
```

```bash
sudo apt install waydroid -y
```

After Installed, run this command to start Waydroid:

```bash
sudo systemctl enable --now waydroid-container
```

**⎙ Restart Waydroid Service**

```bash
sudo systemctl restart waydroid-container
waydroid session stop
waydroid session start
```

**⎙ Set Screen Resolution in Waydroid**

```bash
waydroid prop set persist.waydroid.width 1600
waydroid prop set persist.waydroid.height 900

# Full HD Ratio
waydroid prop set persist.waydroid.width 1920
waydroid prop set persist.waydroid.height 1080
```

### 🗳 Mirror an Android Screen to Linux with Scrcpy

`scrcpy` allows you to display and control your Android device from a Linux desktop. It supports both USB and Wi-Fi connections with low latency and high performance.

**Install Required Packages**

Ubuntu/Debian:

```bash
sudo apt update
sudo apt install adb scrcpy
```

Verify the installation:

```bash
adb version
scrcpy --version
```
#### ☰ Method 1: Mirror via USB (Recommended)

This is the simplest and most reliable method.

**Step 1: Enable Developer Options**

1. Open **Settings** → **About Phone**.
2. Tap **Build Number** 7 times.
3. Enter your PIN or password if prompted.
4. You should see a message indicating that Developer Options have been enabled.

**Step 2: Enable USB Debugging**

1. Open **Settings** → **Developer Options**.
2. Enable **USB Debugging**.

**Step 3: Connect Your Phone**

Connect your Android device to your Linux computer using a USB cable.

**Step 4: Verify the Connection**

Run:

```bash
adb devices
```

Example output:

```text
List of devices attached
R58M123456A    device
```

If a USB debugging authorization prompt appears on your phone, tap **Allow**.

**Step 5: Start Screen Mirroring**

Run:

```bash
scrcpy
```

Your Android screen should now appear on your Linux desktop.

#### ☰ Method 2: Mirror via Wi-Fi

This method requires that your phone and computer are connected to the same network.

**Step 1: Enable Developer Options and USB Debugging**

Follow the steps from Method 1.

**Step 2: Connect via USB**

Connect your phone with a USB cable and verify the connection:

```bash
adb devices
```

**Step 3: Enable TCP/IP Mode**

Run:

```bash
adb tcpip 5555
```

Expected output:

```text
restarting in TCP mode port: 5555
```

**Step 4: Find Your Phone's IP Address**

On your phone:

**Settings** → **Wi-Fi** → **Connected Network**

Note the IP address, for example:

```text
192.168.1.100
```

**Step 5: Connect Wirelessly**

Disconnect the USB cable and run:

```bash
adb connect 192.168.1.100:5555
```

Verify the connection:

```bash
adb devices
```

Example output:

```text
192.168.1.100:5555    device
```

**Step 6: Start Screen Mirroring**

Run:

```bash
scrcpy
```

Or connect directly:

```bash
scrcpy --tcpip=192.168.1.100
```

#### ☰ Android 11+ Wireless Debugging (No USB Required)

Android 11 introduced Wireless Debugging, allowing ADB connections without an initial USB cable.

**Step 1: Enable Wireless Debugging**

1. Open **Settings** → **Developer Options**.
2. Enable **Wireless Debugging**.

**Step 2: Pair the Device**

On your phone:

1. Open **Wireless Debugging**.
2. Tap **Pair Device with Pairing Code**.
3. Note the IP address, pairing port, and pairing code.

Example:

```text
IP Address: 192.168.1.100
Pairing Port: 36543
Pairing Code: 123456
```

Run:

```bash
adb pair 192.168.1.100:36543
```

Enter the pairing code when prompted.

**Step 3: Connect**

Use the connection address shown in Wireless Debugging:

```bash
adb connect 192.168.1.100:5555
```

**Step 4: Start Scrcpy**

```bash
scrcpy
```


#### ☰ Useful `Scrcpy` Commands

**Record the Screen**

```bash
scrcpy --record screen.mp4
```

**Start in Fullscreen Mode**

```bash
scrcpy --fullscreen
```

**Turn Off the Phone Screen While Mirroring**

```bash
scrcpy --turn-screen-off
```

**Set a Custom Resolution**

```bash
scrcpy --max-size 1280
```

**Disable Audio**

```bash
scrcpy --no-audio
```

**Keep the Device Awake**

```bash
scrcpy --stay-awake
```

**Read-Only Mode**

```bash
scrcpy --no-control
```

#### ☰ Troubleshooting

**Device Not Detected**

Check that USB Debugging is enabled:

```bash
adb devices
```

Restart the ADB server:

```bash
adb kill-server
adb start-server
```

#### ☰ Unauthorized Device

If the device appears as `unauthorized`:

1. Disconnect the device.
2. Reconnect it.
3. Accept the USB debugging authorization prompt on the phone.

#### ☰ Connection Refused Over Wi-Fi

Ensure that:

- The phone and computer are on the same network.
- The correct IP address is used.
- TCP/IP mode is enabled:

```bash
adb tcpip 5555
```

Check Connected Devices

```bash
adb devices -l
```

#### ☰ Uninstall

```bash
sudo apt remove adb scrcpy
```

Or remove unused dependencies as well:

```bash
sudo apt autoremove
```

You can now mirror and control your Android device from Linux using either a USB cable or a wireless connection with `scrcpy`.

### 🗳 Cine Video Player

```bash
flatpak install flathub io.github.diegopvlk.Cine
```

# 🗁 Ubuntu: System Utilities 
---
### 🜲 Linux Application

### 🜲 Ubuntu System Info

Install **FastFetch**

```bash
sudo apt install fastfetch
```

Command in Terminal: 

```bash
fastfetch
```

### 🜲 Ubuntu Speed Up (Hacks)

#### 🗳 1. Linux Update & Upgrade

```bash
sudo apt update; sudo apt upgrade -y
```
#### 🗳 2. Linux Drivers

```bash
sudo apt install software-properties-gtk
```

```bash
sudo ubuntu-drivers list
sudo install ubuntu-drivers
```

#### 🗳 3. Unlock Ubuntu-restricted Apps (Pre-installed)

```bash
sudo apt install ubuntu-restricted-extras
```

#### 🗳 4. Linux Firewall

```bash
sudo apt install gufw
```
 
#### 🗳 5. Linux OS Backup (for restore after install new OS)

```bash
sudo apt install timeshift
```

#### 🗳 6. GNOME Tweaks

```bash
sudo apt install gnome-tweaks papirus-icon-theme
```

### 🜲 Flatpak (Package Manager)

Install `Flatpak`

```bash
sudo apt install flatpak
sudo apt install gnome-software-plugin-flatpak
```

### 🜲 Change Ubuntu Password via Terminal

```bash
passwd
```

```bash
sudo passwd root
```

# 🗁 Package Manager
---
### 🜲 Snap packages

**List installed Snap packages**

```bash
snap list
```

Remove a package:

```bash
sudo snap remove package_name
# Example: sudo snap remove firefox
```

### 🜲 Flatpak

**List installed Flatpak applications**

```bash
flatpak list
```

Remove an application

```bash
flatpak uninstall application_id
# flatpak uninstall org.mozilla.firefox
```

**Remove unused Flatpak runtimes**
After uninstalling apps, clean up unused dependencies:

```bash
flatpak uninstall --unused
```

### 🜲 APT (Advanced Package Manager)

APT (Advanced Package Tool) is Ubuntu's default package manager.

#### 🗺️ Update Package Lists

Before installing anything:

```bash
sudo apt update
```

Update installed packages:

```bash
sudo apt upgrade
```

Update everything including dependencies:

```bash
sudo apt full-upgrade
```
#### 🗺️ Search for Packages

Search by name:

```bash
apt search package_name
```

Example:

```bash
apt search nginx
```

Show package details:

```bash
apt show package_name
```

Example:

```bash
apt show nginx
```

#### 🗺️ Install Packages

Install a package:

```bash
sudo apt install package_name
```

Example:

```bash
sudo apt install git
```

Install multiple packages:

```bash
sudo apt install git curl vim
```

#### 🗺️ List Installed Packages

List all installed packages:

```bash
apt list --installed
```

List manually installed packages:

```bash
apt-mark showmanual
```

Find a package:

```bash
apt list --installed | grep package_name
```

Example:

```bash
apt list --installed | grep git
```

#### 🗺️ Check if a Package is Installed

```bash
dpkg -s package_name
```

Example:

```bash
dpkg -s git
```

Alternative:

```bash
dpkg -l | grep package_name
```

#### 🗺️ Remove Packages

Remove package but keep config files:

```bash
sudo apt remove package_name
```

Example:

```bash
sudo apt remove nginx
```

Remove package and configuration files:

```bash
sudo apt purge package_name
```

Example:

```bash
sudo apt purge nginx
```

#### 🗺️ Remove Unused Dependencies

```bash
sudo apt autoremove
```

Remove dependencies and configs:

```bash
sudo apt autoremove --purge
```

#### 🗺️ Clean Package Cache

Clean downloaded package files:

```bash
sudo apt clean
```

Remove outdated cache only:

```bash
sudo apt autoclean
```

#### 🗺️ Reinstall a Package

```bash
sudo apt install --reinstall package_name
```

Example:

```bash
sudo apt install --reinstall git
```

#### 🗺️ Show Package Dependencies

Packages required by a package:

```bash
apt depends package_name
```

Example:

```bash
apt depends nginx
```

Packages that depend on it:

```bash
apt rdepends package_name
```

#### 🗺️ See Recently Installed Packages

```bash
grep " install " /var/log/dpkg.log
```

For older logs:

```bash
zgrep " install " /var/log/dpkg.log*
```

#### 🗺️ Find Which Package Owns a File

Example:

```bash
dpkg -S /usr/bin/git
```

Or:

```bash
dpkg -S $(which git)
```

#### 🗺️ List Package Files

```bash
dpkg -L package_name
```

Example:

```bash
dpkg -L git
```

#### 🗺️ Fix Broken Packages

Configure partially installed packages:

```bash
sudo dpkg --configure -a
```

Fix dependency issues:

```bash
sudo apt --fix-broken install
```
#### 🗺️ Remove Orphaned Packages

```bash
sudo apt autoremove
```

Find manually installed packages:

```bash
apt-mark showmanual
```

#### 🗺️ Upgrade a Single Package

```bash
sudo apt install --only-upgrade package_name
```

Example:

```bash
sudo apt install --only-upgrade firefox
```

#### 🗺️ Simulate Commands (Safe Test)

Before installing:

```bash
sudo apt install --simulate package_name
```

Before removing:

```bash
sudo apt remove --simulate package_name
```

#### 🗺️ Common Daily Commands

Update repositories:

```bash
sudo apt update
```

Upgrade packages:

```bash
sudo apt upgrade
```

Install:

```bash
sudo apt install package_name
```

Remove:

```bash
sudo apt remove package_name
```

Purge:

```bash
sudo apt purge package_name
```

Cleanup:

```bash
sudo apt autoremove --purge
sudo apt clean
```
#### 🗺️ Useful Workflow

Update system:

```bash
sudo apt update && sudo apt upgrade -y
```

Install software:

```bash
sudo apt install git curl vim -y
```

Remove software completely:

```bash
sudo apt purge package_name -y
sudo apt autoremove --purge -y
```

Clean cache:

```bash
sudo apt clean
```

This covers about 95% of what most Ubuntu users and developers need when managing packages with APT.