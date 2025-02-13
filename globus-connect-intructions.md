# Globus Connect

Globus Connect allows you to transfer large output files between servers and from the HPC to your local computer.

---

## Connecting to the HPC Server

1. **Log in** to [Globus Connect](https://www.globus.org/) using your ACCESS ID credentials.
2. **Use your organizational login:** Search for `ACCESS CI (XSEDE)` and select it.
3. Click **Continue**.
4. **Enter your ACCESS credentials** (not PSC) and password.
5. In the **Collection** search bar, type **bridges**.
6. Select the `PSC Bridges-2` collection.
7. In the **Path** box, enter your target directory based on where you want to transfer files to or from:
   - `/jet/home/your-username`
   - `/ocean/projects/agr250001p/your-username`

---

## Downloading and Installing Globus on Your Local Machine

1. **Download** Globus Connect Personal from [this link](https://app.globus.org/collections/gcp).
2. Locate the downloaded installer and **double-click** it to start installation.
3. If a "Windows protected your PC" warning appears, click **More Info**, then **Run Anyway**, and confirm by clicking **Yes**.
4. Follow the on-screen prompts to complete installation, then click **Finish** to launch Globus.
5. *(Optional)* If Globus does not start automatically, search for **Globus** in your system's search bar and open it.
6. **Log in** with your ACCESS credentials.
7. Click **Allow** to complete the Globus Connect Personal setup.
8. Add collection details:
   - **Collection Name:** Choose a name that is easy to recognize (e.g., "My Laptop").
   - **Description:** You can use a description like "Personal computer for file transfers."
9. Click **Save**.

---

## Transferring Files

1. Go back to the **File Manager** in Globus online.
2. Locate the panel bar in the **top-right corner** and select the middle option (two rectangles icon) to split the window.
3. The **HPC collection** will appear on the left side, while the right side will be undefined.
4. Click the **Collection Search Bar** on the right side.
5. Go to the **Your Collections** tab.
6. Select your **personal computer name** from the list.
7. The default transfer directory is **Documents**, so files will be stored there unless changed.
8. To transfer files, simple select the file/folder and click **start**
