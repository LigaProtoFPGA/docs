# Vivado installation (Nexys A7)

> [!CAUTION]
> Set aside about **2 hours** and plenty of free disk space: the league's earlier installs
> with Vitis took around **85 GB**. On Windows, the drive where Vivado is installed must be
> formatted as **NTFS**; FAT32 and exFAT do not work. You only do this once.

## 1. Download the installer

1. Go to the AMD download page: https://www.xilinx.com/support/download.html
2. Find the **Vivado 2025.1** section. Everyone in the league uses the same version, so
   projects open without upgrade prompts.
3. Download the **Self Extracting Web Installer** for your operating system.
4. Log in or create a free AMD account to start the download.

## 2. Install

1. Run the installer and click **Next**.
2. Log in with your AMD account, choose **Download and Install Now** → **Next**.
3. On **Select Product to Install**:
   - Choose **Vivado**. This is all you need to write VHDL or Verilog, simulate, and
     program the board.
   - Choose **Vitis** instead only if you will write C software for a soft processor
     (MicroBlaze). It installs Vivado too, but the download is much larger.
4. On **Select Extra Content**, keep only:

   **Design Tools**
   - [x] Vivado
   - [x] DocNav
   - [x] Vitis and Vitis HLS (only if you chose Vitis above)

   **Devices → 7 Series**
   - [x] Artix-7 FPGAs

> [!IMPORTANT]
> Deselect every other device family. This is what keeps the installation small.

5. Accept the license terms → **Next**.
6. Choose the installation directory → **Next**.
7. Review the summary and click **Install**.

> [!TIP]
> The installation takes between 20 minutes and 2 hours. Stay nearby towards the end: a
> few prompts ask for confirmation, including the cable drivers needed to program the board.

## 3. Install the Nexys A7 board files

Board files let Vivado recognize the Nexys A7 when you create a project.

**Option A, from inside Vivado (recommended)**

1. Open Vivado.
2. Click **Create Project** → **Next** → **Next** until the board selection screen.
3. Click **Refresh** to update the list.
4. Search for **Nexys A7**.
5. Click the download icon next to the board name and confirm.

**Option B, manually from Digilent**

1. Download and extract https://github.com/Digilent/vivado-boards
2. In Vivado, open **Tools → Settings → Vivado Store → Board Repository**.
3. Click **+** and point to the `vivado-boards/new/board_files` folder.
4. Click **OK**, then close and reopen Vivado.

## 4. Choosing the device without board files

If you pick the part manually when creating a project, use:

| Filter | Value |
| --- | --- |
| Family | Artix-7 |
| Package | csg324 |
| Speed | -1 |

and select **xc7a100tcsg324-1** (Nexys A7-100T).

## 5. Done

Your environment is ready. Next:
[`tutorials/vivado/vivado_intro.md`](https://github.com/LigaProtoFPGA/tutorials/blob/main/vivado/vivado_intro.md).
Keep the [Nexys A7 page](../boards/nexys_a7.md) at hand for pins and board settings.
