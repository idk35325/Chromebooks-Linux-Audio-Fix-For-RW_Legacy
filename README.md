# Chromebooks Audio Fix for Linux (rw_legacy)

This project restores working audio (speakers and headphones) on Any Chromebook running Linux, without needing a full ROM Flash.  
Tested on Pop!_OS Ubuntu Lubuntu And Kubuntu. It may work on other Linux distributions — contributions welcome.

# 🎧 chromebooks Audio Fix (rw_legacy)

This project provides a tested **audio fix** ON  ONLY **Blooguard octopus Board** model when running **Linux** with **MrChromebox rw_legacy firmware**.

If you’re using a **full ROM** flash, you NOT need this — this fix is designed for **rw_legacy users** who want to keep ChromeOS boot options but still have working audio in Linux.

---

## 🧩 Overview

Many Chromebook users lose sound after installing Linux via **rw_legacy**.  
This fix restores audio output by restoring known-good **GRUB + ALSA** configurations from a verified backup that has been tested and confirmed working.

**Confirmed working on Chromebooks:**
- 🟢 HP Chromebook x360 14a-ca0  

**Tested Linux distributions:**
- 🟢 Pop!_OS 22.04 / 24.04  
- 🟢 Ubuntu 22.04 / 24.04  
- 🟢 Lubuntu 22.04 / 24.04 
- 🟢 Kubuntu 22.04 / 24.04
  
**Confirmed working on platform processor:**

- 🟢 GEMINI LAKE

** Confirmed working processors:**

- 🟢 INTEL CELERON N4120

**May also work on:**
- 🟡 Linux Mint  
- 🟡 Debian  
- 🟡 Fedora  
- 🟡 Elementary OS  
- 🟡 GalliumOS (with custom kernel)
- 🟡 Arch Linux


If you test and confirm it works on other distros " More Chromebooks Models " platform processor " and processors   , please open an **issue** or **pull request** so we can update the list!

⚙️ Installation (Manual Method)

1. Install neno 

sudo apt install nano

sudo dnf install nano

sudo pacman -S nano


If you already have nano installed, you can manually add the audio fix to GRUB.

2. Open the GRUB configuration file

sudo nano /etc/default/grub

3. Find the line

GRUB_CMDLINE_LINUX_DEFAULT=

change TO

GRUB_CMDLINE_LINUX_DEFAULT="quiet splash snd_intel_dspcfg.dsp_driver=3"

💡 Important: Do not change the _DEFAULT part — that’s the correct GRUB variable name.

4. Save and exit nano

Press Ctrl + O → then Enter to save

Press Ctrl + X to exit

5. Update GRUB

sudo update-grub

6. Reboot your Chromebook

sudo reboot


✅ After reboot, your sound (speakers and headphone jack) should now work.

## ⚡ Features / Why It Works

- Forces the Intel audio driver to use the legacy HDA audio interface.
- Works with rw_legacy firmware (no full ROM update required).
- Tested on Pop!_OS Ubuntu Lubuntu and Kubuntu.
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

MIT License

Copyright (c) 2025 idk35325

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
