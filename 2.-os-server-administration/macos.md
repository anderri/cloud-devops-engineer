---
description: https://git.herrbischoff.com/awesome-macos-command-line/about/#networking
---

# MacOs

### Disable Gatekeeper and open blocked application by "Unidentified developer"

```
sudo spctl --master-disable
```

### Neofetch&#x20;

Displays information about your operating system, software and hardware in an aesthetic and visually pleasing way.

```
brew install neofetch
```

### ZSH Auto-suggestions

ZSH is a popular Unix shell that extends the Bourne Again Shell. It comes packed with features and improvements over Bash. If you are a regular terminal user, having an exceptional terminal session will improve your workflow and help you enjoy using the terminal..

```
brew install zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
```

### [Networking](https://git.herrbischoff.com/awesome-macos-command-line/about/#networking) <a href="#networking" id="networking"></a>

#### [Bonjour](https://git.herrbischoff.com/awesome-macos-command-line/about/#bonjour) <a href="#bonjour" id="bonjour"></a>

[**Bonjour Service**](https://git.herrbischoff.com/awesome-macos-command-line/about/#bonjour-service)

```
# Disable
sudo defaults write /System/Library/LaunchDaemons/com.apple.mDNSResponder.plist ProgramArguments -array-add "-NoMulticastAdvertisements"

# Enable (Default)
sudo defaults write /System/Library/LaunchDaemons/com.apple.mDNSResponder.plist ProgramArguments -array "/usr/sbin/mDNSResponder" "-launchd"
```

#### [DHCP](https://git.herrbischoff.com/awesome-macos-command-line/about/#dhcp) <a href="#dhcp" id="dhcp"></a>

[**Renew DHCP Lease**](https://git.herrbischoff.com/awesome-macos-command-line/about/#renew-dhcp-lease)

```
sudo ipconfig set en0 DHCP
```

[**Show DHCP Info**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-dhcp-info)

```
ipconfig getpacket en0
```

#### [DNS](https://git.herrbischoff.com/awesome-macos-command-line/about/#dns) <a href="#dns" id="dns"></a>

[**Clear DNS Cache**](https://git.herrbischoff.com/awesome-macos-command-line/about/#clear-dns-cache)

```
sudo dscacheutil -flushcache && \
sudo killall -HUP mDNSResponder
```

#### [Hostname](https://git.herrbischoff.com/awesome-macos-command-line/about/#hostname) <a href="#hostname" id="hostname"></a>

[**Set Computer Name/Host Name**](https://git.herrbischoff.com/awesome-macos-command-line/about/#set-computer-namehost-name)

```
sudo scutil --set ComputerName "newhostname" && \
sudo scutil --set HostName "newhostname" && \
sudo scutil --set LocalHostName "newhostname" && \
sudo defaults write /Library/Preferences/SystemConfiguration/com.apple.smb.server NetBIOSName -string "newhostname"
```

#### [Network Preferences](https://git.herrbischoff.com/awesome-macos-command-line/about/#network-preferences) <a href="#network-preferences" id="network-preferences"></a>

[**Network Locations**](https://git.herrbischoff.com/awesome-macos-command-line/about/#network-locations)

Switch between network locations created in the Network preference pane.

```
# Status
scselect

# Switch Network Location
scselect LocationNameFromStatus
```

[**Set Static IP Address**](https://git.herrbischoff.com/awesome-macos-command-line/about/#set-static-ip-address)

```
networksetup -setmanual "Ethernet" 192.168.2.100 255.255.255.0 192.168.2.1
```

#### [Networking Tools](https://git.herrbischoff.com/awesome-macos-command-line/about/#networking-tools) <a href="#networking-tools" id="networking-tools"></a>

[**Ping a Host to See Whether It’s Available**](https://git.herrbischoff.com/awesome-macos-command-line/about/#ping-a-host-to-see-whether-its-available)

```
ping -o herrbischoff.com
```

[**Troubleshoot Routing Problems**](https://git.herrbischoff.com/awesome-macos-command-line/about/#troubleshoot-routing-problems)

```
traceroute herrbischoff.com
```

#### [SSH](https://git.herrbischoff.com/awesome-macos-command-line/about/#ssh) <a href="#ssh" id="ssh"></a>

[**Permanently Add Private Key Passphrase to SSH Agent**](https://git.herrbischoff.com/awesome-macos-command-line/about/#permanently-add-private-key-passphrase-to-ssh-agent)

> Prior to macOS 10.12 (Sierra), ssh would present a dialog asking for your passphrase and would offer the option to store it into the keychain. This UI was deprecated some time ago and has been removed.
>
> Instead, a new UseKeychain option was introduced in macOS 10.12 (Sierra) allowing users to specify whether they would like for the passphrase to be stored in the keychain. This option was enabled by default on macOS 10.12 (Sierra), which caused all passphrases to be stored in the keychain.
>
> This was not the intended default behavior, so this has been changed in macOS 10.12.2. ([Source](https://developer.apple.com/library/archive/technotes/tn2449/\_index.html))

```
ssh-add -K /path/to/private_key
```

Then add to `~/.ssh/config`:

```
Host server.example.com
    IdentityFile /path/to/private_key
    UseKeychain yes
```

[**Remote Login**](https://git.herrbischoff.com/awesome-macos-command-line/about/#remote-login)

```
# Enable
sudo launchctl load -w /System/Library/LaunchDaemons/ssh.plist

# Disable (Default)
sudo launchctl unload -w /System/Library/LaunchDaemons/ssh.plist
```

#### [TCP/IP](https://git.herrbischoff.com/awesome-macos-command-line/about/#tcpip) <a href="#tcpip" id="tcpip"></a>

[**Show Application Using a Certain Port**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-application-using-a-certain-port)

This outputs all applications currently using port 80.

```
sudo lsof -i :80
```

[**Show External IP Address**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-external-ip-address)

Works if your ISP doesn't replace DNS requests (which it shouldn't).

```
dig +short myip.opendns.com @resolver1.opendns.com
```

Alternative that works on all networks.

```
curl -s https://api.ipify.org && echo
```

[**Show Network Interface Information**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-network-interface-information)

Undocumented flag of the `scutil` command.

```
scutil --nwi
```

#### [TFTP](https://git.herrbischoff.com/awesome-macos-command-line/about/#tftp) <a href="#tftp" id="tftp"></a>

[**Start Native TFTP Daemon**](https://git.herrbischoff.com/awesome-macos-command-line/about/#start-native-tftp-daemon)

Files will be served from `/private/tftpboot`.

```
sudo launchctl load -F /System/Library/LaunchDaemons/tftp.plist && \
sudo launchctl start com.apple.tftpd
```

#### [Wi-Fi](https://git.herrbischoff.com/awesome-macos-command-line/about/#wi-fi) <a href="#wi-fi" id="wi-fi"></a>

[**Join a Wi-Fi Network**](https://git.herrbischoff.com/awesome-macos-command-line/about/#join-a-wi-fi-network)

```
networksetup -setairportnetwork en0 WIFI_SSID WIFI_PASSWORD
```

[**Scan Available Access Points**](https://git.herrbischoff.com/awesome-macos-command-line/about/#scan-available-access-points)

Create a symbolic link to the airport command for easy access:

```
sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport
```

Run a wireless scan:

```
airport -s
```

[**Show Current SSID**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-current-ssid)

```
/System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport -I | awk '/ SSID/ {print substr($0, index($0, $2))}'
```

[**Show Local IP Address**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-local-ip-address)

```
ipconfig getifaddr en0
```

[**Show Wi-Fi Connection History**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-wi-fi-connection-history)

```
defaults read /Library/Preferences/SystemConfiguration/com.apple.airport.preferences | grep LastConnected -A 7
```

[**Show Wi-Fi Network Passwords**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-wi-fi-network-passwords)

Exchange SSID with the SSID of the access point you wish to query the password from.

```
security find-generic-password -D "AirPort network password" -a "SSID" -gw
```

[**Turn on Wi-Fi Adapter**](https://git.herrbischoff.com/awesome-macos-command-line/about/#turn-on-wi-fi-adapter)

```
networksetup -setairportpower en0 on
```

\


### [System](https://git.herrbischoff.com/awesome-macos-command-line/about/#system) <a href="#system" id="system"></a>

#### [AirDrop](https://git.herrbischoff.com/awesome-macos-command-line/about/#airdrop) <a href="#airdrop" id="airdrop"></a>

[**AirDrop over Ethernet on Unsupported Macs**](https://git.herrbischoff.com/awesome-macos-command-line/about/#airdrop-over-ethernet-on-unsupported-macs)

```
# Enable
defaults write com.apple.NetworkBrowser BrowseAllInterfaces -bool true && \
defaults remove com.apple.NetworkBrowser DisableAirDrop

# Disable (Default)
defaults delete com.apple.NetworkBrowser BrowseAllInterfaces && \
defaults write com.apple.NetworkBrowser DisableAirDrop -bool true
```

#### [AppleScript](https://git.herrbischoff.com/awesome-macos-command-line/about/#applescript) <a href="#applescript" id="applescript"></a>

[**Execute AppleScript**](https://git.herrbischoff.com/awesome-macos-command-line/about/#execute-applescript)

```
osascript /path/to/script.scpt
```

#### [Basics](https://git.herrbischoff.com/awesome-macos-command-line/about/#basics) <a href="#basics" id="basics"></a>

[**Compare Two Folders**](https://git.herrbischoff.com/awesome-macos-command-line/about/#compare-two-folders)

```
diff -qr /path/to/folder1 /path/to/folder2
```

[**Copy Large File with Progress**](https://git.herrbischoff.com/awesome-macos-command-line/about/#copy-large-file-with-progress)

Make sure you have `pv` installed and replace `/dev/rdisk2` with the appropriate write device or file.

```
FILE=/path/to/file.iso pv -s $(du -h $FILE | awk '/.*/ {print $1}') $FILE | sudo dd of=/dev/rdisk2 bs=1m
```

[**Restore Sane Shell**](https://git.herrbischoff.com/awesome-macos-command-line/about/#restore-sane-shell)

In case your shell session went insane (some script or application turned it into a garbled mess).

```
stty sane
```

[**Restart**](https://git.herrbischoff.com/awesome-macos-command-line/about/#restart)

```
sudo reboot
```

[**Shutdown**](https://git.herrbischoff.com/awesome-macos-command-line/about/#shutdown)

```
sudo poweroff
```

[**Show Build Number of OS**](https://git.herrbischoff.com/awesome-macos-command-line/about/#show-build-number-of-os)

```
sw_vers
```

[**Uptime**](https://git.herrbischoff.com/awesome-macos-command-line/about/#uptime)

How long since your last restart.

```
uptime
```

#### [Clipboard](https://git.herrbischoff.com/awesome-macos-command-line/about/#clipboard) <a href="#clipboard" id="clipboard"></a>

[**Copy data to Clipboard**](https://git.herrbischoff.com/awesome-macos-command-line/about/#copy-data-to-clipboard)

```
cat whatever.txt | pbcopy
```

[**Convert Clipboard to Plain Text**](https://git.herrbischoff.com/awesome-macos-command-line/about/#convert-clipboard-to-plain-text)

```
pbpaste | textutil -convert txt -stdin -stdout -encoding 30 | pbcopy
```

[**Convert Tabs to Spaces for Clipboard Content**](https://git.herrbischoff.com/awesome-macos-command-line/about/#convert-tabs-to-spaces-for-clipboard-content)

```
pbpaste | expand | pbcopy
```

[**Copy data from Clipboard**](https://git.herrbischoff.com/awesome-macos-command-line/about/#copy-data-from-clipboard)

```
pbpaste > whatever.txt
```

[**Sort and Strip Duplicate Lines from Clipboard Content**](https://git.herrbischoff.com/awesome-macos-command-line/about/#sort-and-strip-duplicate-lines-from-clipboard-content)

```
pbpaste | sort | uniq | pbcopy
```

#### [FileVault](https://git.herrbischoff.com/awesome-macos-command-line/about/#filevault) <a href="#filevault" id="filevault"></a>

[**Automatically Unlock FileVault on Restart**](https://git.herrbischoff.com/awesome-macos-command-line/about/#automatically-unlock-filevault-on-restart)

If FileVault is enabled on the current volume, it restarts the system, bypassing the initial unlock. The command may not work on all systems.

```
sudo fdesetup authrestart
```

[**FileVault Service**](https://git.herrbischoff.com/awesome-macos-command-line/about/#filevault-service)

```
# Status
sudo fdesetup status

# Enable
sudo fdesetup enable

# Disable (Default)
sudo fdesetup disable
```

#### [Installation](https://git.herrbischoff.com/awesome-macos-command-line/about/#installation) <a href="#installation" id="installation"></a>

[**Create Bootable Installer**](https://git.herrbischoff.com/awesome-macos-command-line/about/#create-bootable-installer)

```
# macOS 13 (Ventura)
sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets

# macOS 12 (Monterey)
sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets

# macOS 11 (Big Sur)
sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets

# macOS 10.15 (Catalina)
sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets

# macOS 10.14 (Mojave)
sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets

# macOS 10.13 (High Sierra)
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --applicationpath /Applications/Install\ macOS\ High\ Sierra.app

# macOS 10.12 (Sierra)
sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --applicationpath /Applications/Install\ macOS\ Sierra.app

# OS X 10.11 (El Capitan)
sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app

# OS X 10.10 (Yosemite)
sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --applicationpath /Applications/Install\ OS\ X\ Yosemite.app
```

* For confirmation before erasing the drive, remove `–-nointeraction` from the command.
* The optional `–-downloadassets` flag is new in macOS 10.14 (Mojave). It downloads assets which may be required during installation, like updates.
* The `–-applicationpath` flag is deprecated since macOS 10.14 (Mojave) and will throw an error if used.

[**Download Older OS Versions**](https://git.herrbischoff.com/awesome-macos-command-line/about/#download-older-os-versions)

| Version       | Codename      | Download                                                                                                                                 |
| ------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Mac OS X 10.0 | Cheetah       | n/a                                                                                                                                      |
| Mac OS X 10.1 | Puma          | n/a                                                                                                                                      |
| Mac OS X 10.2 | Jaguar        | n/a                                                                                                                                      |
| Mac OS X 10.3 | Panther       | n/a                                                                                                                                      |
| Mac OS X 10.4 | Tiger         | n/a                                                                                                                                      |
| Mac OS X 10.5 | Leopard       | n/a                                                                                                                                      |
| Mac OS X 10.6 | Snow Leopard  | n/a                                                                                                                                      |
| Mac OS X 10.7 | Lion          | [Direct Download](https://updates.cdn-apple.com/2021/macos/041-7683-20210614-E610947E-C7CE-46EB-8860-D26D71F0D3EA/InstallMacOSX.dmg)     |
| OS X 10.8     | Mountain Lion | [Direct Download](https://updates.cdn-apple.com/2021/macos/031-0627-20210614-90D11F33-1A65-42DD-BBEA-E1D9F43A6B3F/InstallMacOSX.dmg)     |
| OS X 10.9     | Mavericks     | n/a                                                                                                                                      |
| OS X 10.10    | Yosemite      | [Direct Download](http://updates-http.cdn-apple.com/2019/cert/061-41343-20191023-02465f92-3ab5-4c92-bfe2-b725447a070d/InstallMacOSX.dmg) |
| OS X 10.11    | El Capitan    | [Direct Download](http://updates-http.cdn-apple.com/2019/cert/061-41424-20191024-218af9ec-cf50-4516-9011-228c78eda3d2/InstallMacOSX.dmg) |
| macOS 10.12   | Sierra        | [Direct Download](http://updates-http.cdn-apple.com/2019/cert/061-39476-20191023-48f365f4-0015-4c41-9f44-39d3d2aca067/InstallOS.dmg)     |
| macOS 10.13   | High Sierra   | [App Store](https://apps.apple.com/de/app/macos-high-sierra/id1246284741)                                                                |
| macOS 10.14   | Mojave        | [App Store](https://apps.apple.com/de/app/macos-mojave/id1398502828)                                                                     |
| macOS 10.15   | Catalina      | [App Store](https://apps.apple.com/de/app/macos-catalina/id1466841314)                                                                   |
| macOS 11      | Big Sur       | [App Store](https://apps.apple.com/de/app/macos-big-sur/id1526878132)                                                                    |
| macOS 12      | Monterey      | [App Store](https://apps.apple.com/de/app/macos-monterey/id1576738294)                                                                   |
| macOS 13      | Ventura       | [App Store](https://apps.apple.com/de/app/macos-ventura/id1638787999)                                                                    |

\


