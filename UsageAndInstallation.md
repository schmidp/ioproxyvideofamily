# Introduction #

Unlike other kernel extensions, IOFramebuffer subclasses may not be installed at runtime with kextload.

# Installation Procedure #

```
sudo cp -R IODummyFramebuffer.kext /System/Library/Extensions/
sudo cp -R IODummyVideoCard.kext /System/Library/Extensions/
sudo touch /System/Library/Extensions
sync
reboot
```


# Configuration Details #

Edit the Info.plist file in IODummyVideoCard.kext to change resolutions or add more heads. Empty dictionaries in the HeadList array provide additional displays with default settings.

```
<key>com_doequalsglory_driver_HeadList</key>
<array>
	<dict>
		<key>enabled</key>
		<true/>
		<key>height</key>
		<integer>1050</integer>
		<key>maxHeight</key>
		<integer>1200</integer>
		<key>maxWidth</key>
		<integer>1920</integer>
		<key>name</key>
		<string>DEG,DummyVideoHead_A</string>
		<key>width</key>
		<integer>1400</integer>
	</dict>
	<dict/>
	<dict/>
</array>
```