# ISE 14.7 VM Installation (Nexys 1 and 2)

> [!CAUTION]
> You will need at least **20 GB** of free disk space and a lot of patience — some steps take a long time.

---

## 📦 1. Download Packages

- **Oracle VirtualBox 7.1.0** → [Download](https://download.virtualbox.org/virtualbox/7.1.0/VirtualBox-7.1.0-164728-Win.exe)
- **VirtualBox Extension Pack 7.1.0** → [Download](https://download.virtualbox.org/virtualbox/7.1.0/Oracle_VirtualBox_Extension_Pack-7.1.0.vbox-extpack)
- **ISE 14.7 VM (AMD/Xilinx)** — a free AMD account may be required → [Download](https://www.xilinx.com/downloadNav/vivado-design-tools/archive-ise.html) *(+15 GB, choose the Windows 10 version)*

---

## 🔧 2. Prerequisites before installing VirtualBox

If the VirtualBox installer complains about dependencies, install them in this order:

**2.1 — Microsoft Visual C++ 2019 Redistributable**
→ [Download vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)

**2.2 — Python**
→ [Download python-3.12.6-amd64.exe](https://www.python.org/ftp/python/3.12.6/python-3.12.6-amd64.exe) *(in this version, the command is `py`, not `python`)*

**2.3 — Win32 API (pywin32)**
Open the Command Prompt and run:

`py -m pip install --upgrade pywin32`

---

## ⚙️ 3. Install VirtualBox

1. Install VirtualBox normally.
2. When opening for the first time, accept the installation of the **Extension Pack** (the `.vbox-extpack` file downloaded in step 1).

---

## 📂 4. Import the ISE 14.7 VM

1. Unzip the file downloaded from AMD *(this takes a while)*.
2. Open VirtualBox → **File** menu → **Import Appliance**.
3. Navigate to the `14.7_VM.ova` file inside the folder `Xilinx_ISE_14.7_Win10_14.7_VM_0213_1\ova`.
4. Confirm the import *(this also takes a long time)*.

> [!TIP]
> The files are also available on a 128 GB flash drive — contact Professor Ney.

---

## 🛠️ 5. Configure the VM before running

With the VM **turned off**, open its settings in VirtualBox:

**5.1 — Memory**
In **System**, reduce the memory to **1909 MB** (it should be less than half of your PC's RAM).

**5.2 — Graphics Controller**
In **Display**, keep the **VBoxSVGA** option.

**5.3 — Network**
In **Network → Adapter 1**, select **NAT** in the "Attached to:" menu.

**5.4 — Shared Folder** *(to access your projects inside the VM)*
In **Shared Folders**, add a new folder:

- Path: `C:\Xilinx\ise_projs` (or wherever you saved your work)
- Name: `ise_projs`
- Check **Auto-mount** → OK

To create a shortcut on the VM's Desktop, open a terminal inside the VM and run:

`cd /home/ise/Desktop && ln -s /home/ise/ise_projs ise_projs`

---

## 🔑 6. Configure the License

Open a terminal inside the VM and edit the `~/.bashrc` file:

`nano /home/ise/.bashrc`

Add the following two lines at the end of the file:

`export LM_LICENSE_FILE=2100@172.65.212.135:8888`
`export XILINXD_LICENSE_FILE=2100@paxos.inf.pucrs.br:8888`

Save with `Ctrl+O` and exit with `Ctrl+X`.

Then, edit the ISE launch script:

`cd /opt/Xilinx/14.7/ISE_DS/common`
`sudo nano app_launcher.sh`

Right below the first line (`#!/bin/bash`), add:

`source /home/ise/.bashrc`

Save and exit.

---

## ⚠️ 7. License error during "Map"?

If a license error appears during the **Implement Design → Map** step, follow these steps:

1. Note the `hostid` mentioned in the error.
2. Close the VM.
3. In VirtualBox, go to **Network → Adapter 1 → Advanced**.
4. Change the **MAC Address** to: `08002768C935`
5. Click OK and run the VM again.

---

## ✅ 8. All set!

The environment is configured. Now just follow the first tutorials on the league's GitHub to start working with the board:

🔗 *GitHub link coming soon*
