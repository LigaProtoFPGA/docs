# Vivado + Vitis Installation Guide (Nexys A7 — Artix-7)

> [!CAUTION]
> Allocate at least **2 hours** and **85 GB** of disk space. This is a heavy installation, but it only needs to be done once.

---

## 1. Download the Installer

1. Access the AMD/Xilinx download page:
   https://www.xilinx.com/support/download.html
2. Locate the **Vivado™ Edition — 2025.1** section.
3. Select the **Self Extracting Web Installer** for your operating system.
4. Log in or create a free account to start the download.

---

## 2. Install Vivado + Vitis

1. Run the downloaded installer and click **Next**.
2. Log in with your AMD account and select **Download and Install Now** → **Next**.
3. On the **Select Product to Install** screen, choose **Vitis**. 
   *(Note: This installs both Vitis and Vivado together — do not choose Vivado only).*
4. On the **Select Extra Content** screen, ensure only the following are selected:

   **Design Tools:**
   - [x] Vitis
   - [x] Vivado
   - [x] Vitis HLS
   - [x] DocNav

   **Devices — 7 Series:**
   - [x] Artix-7 FPGAs

> [!IMPORTANT]
> Deselect everything not listed above. This significantly reduces the installation size.

5. Accept all license terms → **Next**.
6. Choose the installation directory → **Next**.
7. Review the summary and click **Install**.

> [!TIP]
> Installation can take anywhere from 20 minutes to 2 hours. Stay nearby towards the end, as a few prompts may appear requesting confirmation.

---

## 3. Install Nexys A7 Board Files

Board Files allow Vivado to automatically recognize your hardware, making project creation much easier.

**Option A — Directly via Vivado (Recommended):**

1. Open Vivado from the Start menu.
2. Click **Create Project** → **Next** → **Next**.
3. When you reach the board selection screen, click **Refresh** to update the list.
4. Search for **Nexys A7** in the search bar.
5. Click the download icon next to the board name and confirm.

**Option B — Via Digilent GitHub (Manual):**

1. Download and extract the board files from the official repository: https://github.com/Digilent/vivado-boards
2. In Vivado, go to **Tools → Settings**.
3. Navigate to **Vivado Store → Board Repository**.
4. Click the **+** icon and point to the `vivado-boards/new/board_files` folder.
5. Click **OK**, then close and reopen Vivado.

---

## 4. Selecting the Correct Nexys A7 Device

When creating a new project, if you are selecting the device manually instead of using the board file, use these filters:

- **Category:** General Purpose
- **Family:** Artix-7
- **Package:** csg324
- **Speed:** -1

Select the device that matches these specifications (xc7a100tcsg324-1) and click **Next**. Review the **New Project Summary** and click **Finish**.

---

## 5. Setup Complete

Your environment is now configured. You can follow the introductory tutorials in the league's repository to start working with the board.

🔗 *Repository link coming soon*
