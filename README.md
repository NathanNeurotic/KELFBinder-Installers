# KELFBinder: UMCS Installer

**Forked from KELFBinder by [El_isra](https://israpps.github.io/) and modified by [NathanNeurotic](https://github.com/NathanNeurotic)**

Unified Memory Card System (UMCS) is a structural standard created by [TnA-Plastic](https://github.com/TnA-Plastic), consolidating exploits and updates into a unified setup. [Learn more](https://www.psx-place.com/forums/ps2-application-system.279/).

## Included Applications & Modules:
- **BOOT.ELF**: [PS2BBL-MMCE](https://israpps.github.io/PlayStation2-Basic-BootLoader/) by [israpps](https://github.com/israpps)
- **BOOT2.ELF**: [wLaunchELF EXFAT-MMCE](https://israpps.github.io/projects/wlaunchelf-isr) by [israpps](https://github.com/israpps) (Hold `Start` during boot for emergency access)
- **OSDMENU.ELF**: [PS2BBL-OSDMENU](https://github.com/pcm720/PlayStation2-Basic-BootLoader) linked to [OSDMENU](https://github.com/pcm720/osdmenu-launcher) by [pcm720](https://github.com/pcm720)
- **launcher.elf & patcher.elf**: [OSDMENU Launcher & Loader](https://github.com/pcm720/osdmenu-launcher) by [pcm720](https://github.com/pcm720)
- **neutrino**: [Neutrino](https://github.com/rickgaiser/neutrino) by [rickgaiser](https://github.com/rickgaiser)
- **nhddl**: [NHDDL](https://github.com/pcm720/nhddl/releases/tag/nightly) by [pcm720](https://github.com/pcm720)
- **POPSTARTER exFAT USB Drivers**: [BDM Assault](https://github.com/israpps/BDMAssault) by [israpps](https://github.com/israpps)
- **POPSTARTER SMB Modules**: [SMB POPSTARTER](https://bitbucket.org/ShaolinAssassin/popstarter-documentation-stuff/wiki/quickstart-smb) by [ShaolinAssassin](https://github.com/ShaolinAssassin)
- **DKWDRV**: [GitHub Repository](https://github.com/DKWDRV/DKWDRV)
- **ESR Launcher** (Manual Launch): by [HowlingWolfHWC](https://github.com/HowlingWolfHWC)
- **FMCB Versions**:
  - FMCB 1.953 & FMCB 1.966 Decrypted ([FreeMcBoot](https://israpps.github.io/FreeMcBoot-Installer/))
  - FMCB Configurator ([FreeMcBoot Configurator](https://israpps.github.io/FreeMcBoot-Installer/))
- **SAS-Compliant Installation** ([PS2Wiki](https://ps2wiki.github.io/sas-apps-archive/))
- **Custom Icon modifications**: by [koraxial](https://github.com/koraxial), [NathanNeurotic](https://github.com/NathanNeurotic)

### UMCS Required Directories:
- **SYS-CONF**: Contains universal configurations for many applications and exploits.
- **BOOT**: Contains the heart of UMCS, contains essential ELFs and their local settings.
- **B?EXEC-SYSTEM**: PS2BBL Exploit relevant to your console(s) region(s).
- **FMCBD-1.??**, or **OSDMENU**: At least one of the three available boots to land on. Otherwise you will only have the option to hold start to access wLaucnhELF.

## Configuration & Boot Order:
By default, the boot sequence searches in this order:

1. **FMCB 1.966** *(Recommended for most users)*  
   - If working, you may safely delete FMCB 1.953, RESTART, and POWEROFF.

2. **FMCB 1.953** *(Fallback if 1.966 fails due to modchips or hardware incompatibilities)*
   - If 1.966 fails, delete it to automatically revert to 1.953.

3. **OSDMENU** *(Alternative launcher if both FMCB versions fail)*
   - If both FMCB versions are incompatible, delete them to activate OSDMENU automatically.

### Emergency Access:
If all three primary boot options fail:
- Hold `Start` during boot to launch **wLaunchELF_EXFAT-MMCE** (BOOT2.ELF).
- Modify launch order or applications via:
  - `mc?:/SYS-CONF/PS2BBL.INI`
  - `mc?:/BOOT/CONFIG.INI`
  - `mc?:/SYS-CONF/PSXBBL.INI`
- Alternative launchers (e.g., `mc?:/NEUTRINO/nhddl.elf`) can be configured using wLaunchELF's built-in text editor.

### Additional Notes:
- Applications are accessible if installed; however, removing unused applications via the PS2 Browser (Memory Card Icon Screen) is recommended to free space.
- Customize boot preferences by editing `mc?:/SYS-CONF/PS2BBL.INI`.
- PSX consoles (PSX-DESR) default to launching wLaunchELF (configured via `PSXBBL.INI`).
- OSDMENU settings (`OSDMENU.CNF`) can be customized via wLaunchELF.

### Compatibility with Late PS2 Slim Models:
Install any form of update, and then launch the included OpenTuna installer to gain access to your UMCS installation.


---------------------------------------------------------------------
# 📂 HOW TO INSTALL – SIMPLE INSTRUCTIONS

Welcome! Follow the steps below carefully to set everything up.  
No need to change, rename, or move anything outside of what’s explained here.

---

## ✅ WHAT YOU'LL NEED:

- One **SD card** (exfat/fat32 mbr)
- One **MMCE Device** (sd2psxtd/MemCard Pro 2/etc)
- One **USB drive**  (exfat/fat32 mbr)
  > Must be formatted as **FAT32** or **exFAT** with **MBR (Master Boot Record)**  
  > Need help formatting? Use [rufus.ie](https://rufus.ie) — it’s simple and free.

---

## 📥 STEP-BY-STEP INSTRUCTIONS

### 1. Prepare the SD Card

- Insert your **SD card** into your computer.
- Open it to view its contents — this is the **"root"** of the SD card.
- Now open the folder named: `!COPY TO SD!` (the one you're reading this in)
- Inside, you’ll see folders like:
  - `APPS`
  - `BOOT`
  - `NEUTRINO`
  - (others, if included)

➡️ **Copy all of these folders** and **paste them directly onto the SD card root**.  
> Do **not** put them in another folder.

🔁 If asked **"Do you want to replace or merge folders?"** click **YES**, **REPLACE**, or **MERGE** – that’s okay.

Once done, **safely eject the SD card**.

---

### 2. Prepare the USB Drive

- Insert your **USB drive** into your computer.
- **Do not change the folder structure** of the KELFBinder installer package.
- Simply **copy the entire installer package as-is** (all files and folders) to the **root of your USB drive**.

> The USB should now contain:
> - `KELFBinder.elf`
> - All included related installer files/folders it came with
> - No extra folders or rearrangements

Once done, **safely eject the USB drive**.

---

## 🧩 FINAL STEP – INSTALL UMCS

1. Plug both the **SD card** into your MMCE device and the **USB drive** into your PS2.

2. On your device, **run `KELFBinder.elf` from the USB drive**.  
   > This will start the UMCS installation which will expect the files from the SD card to be present on your MMCE device.

---

## ❌ DON'T DO THIS:

- ❌ Don’t copy the `!COPY TO SD!` folder itself — only its **contents**.
- ❌ Don’t move any installer files from the USB package.
- ❌ Don’t rename or delete anything.
- ❌ Don’t put the installer on the SD card — it **must** run from USB.

---

## 💡 NEED HELP?

If you're unsure about anything, don’t worry — take your time and re-read the steps.  
Ask for help in the community if needed — we’re happy to support you!

---

---------------------------------------------------------------------
ORIGINAL README:
---------------------------------------------------------------------
DVDPlayer and System Updates Manager for SCE PlayStation2

![GitHub all releases](https://img.shields.io/github/downloads/israpps/KELFBinder/total)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/8e886d46292e4d558c1c35a3387bffd5)](https://app.codacy.com/gh/israpps/KELFBinder/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)

[![](https://img.shields.io/badge/Read%20the-Documentation-0020ff?style=for-the-badge&logo=pencil&labelColor=yellow)](https://israpps.github.io/KELFBinder/)


<details>
  <summary>Preview Images</summary>
  

![IMG1](./img/img1.png)
![IMG2](./img/img2.png)
![IMG3](./img/img3.png)
![IMG4](./img/img4.png)
![IMG5](./img/img5.png)
![IMG6](./img/img6.png)
![IMG7](./img/img7.png)
![IMG8](./img/img8.png)

</details>

