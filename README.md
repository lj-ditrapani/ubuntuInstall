## Step 1
- Download Ubuntu 16.04.3 and copy to usb device

```
dd bs=512 if=path/to/ubuntu.iso of=/dev/sd? status=progress  # where ? is the usb device
```

- Check "Download updates while installing ubuntu"
- Select "Erase disk and install ubuntu"
- Timezone New York

## Step 2
- Configure system and install packages:

```bash
    wget -O - https://goo.gl/UjTi9R | bash
```

- Log out and log back in for group assignments & user settings to take effect

## Optional Steps

#### Change font to Adobe Source Code Pro
- in you `gnome-terminal` you should change the font to Adobe Source Code Pro Medium 11
- Also hide the menu bar (you can just right click anywhere in the terminal and get the same outcome)

#### Increasing audio fidelity
*NOTE*: These are automatically added by this install script. If you wish to change them or remove them, this info is helpful. You should keep them
though, for the sweet sweet fidelity.

  - open the pulseaudio daemon conf `sudo vim /etc/pulse/daemon.conf`
  - uncomment (by deleting `;` and change the following lines:

```
resample-method = src-sinc-medium-quality
default-sample-format = s24le
default-sample-rate = 48000
```
  
  - restart pulseaudio

```
pulseaudio -k
pulseaudio --start
```

  - check that it worked

```
pacmd list-sinks | grep sample
=> sample spec: s32le 2ch 44100Hz
```

#### TODO
- intellij
- scala
