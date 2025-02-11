# Installing and Using `rsync` on Windows and Mac

## Installing `rsync`

### Windows
Windows does not come with `rsync` by default. However, since all of you have Git Bash installed, you can install `rsync` manually for use within Git Bash.

#### Installing `rsync` in MSYS2
1. Download executable **MSYS2** from [https://www.msys2.org/](https://github.com/msys2/msys2-installer/releases/download/2024-12-08/msys2-x86_64-20241208.exe).
2. Doble clink on the installer `msys2-x86_64-20241208.exe`
3. Follow the prompts to install.
4. The final step asks you to ckeck a box to open MSYS2 after the installation. Make sure box is checked.
5. (Optional) Open the **MSYS2 UCRT64** terminal from the Start menu.
6. The MSYS2 looks identical to the git bash terminal.
7. Update the package list and install `rsync` by running:
   ```sh
   pacman -Syu
   #Here it will ask if you want to proceed with installation, type `Y`
   #Will ask to close the window after installation is finished. Type `Y`
```
8. Open the **MSYS2 UCRT64** from the start menu terminal again and type
``` bash
pacman -S rsync
#Here it will ask if you want to proceed with installation, type `Y`
```
9. Confirm installation, on the MSYS2 terminal type:
   ```sh
   rsync --version
   ```
5. Now you can use `rsync` from the *MSYS2* terminal

### macOS
`rsync` is pre-installed on macOS. However, you may want to install an updated version using Homebrew:
```sh
brew install rsync
```

## Using `rsync` for File Transfers

### Download Files from HPC to Local computer
```sh
rsync -rltpDvp -e "ssh -l your-psc-username " your-psc-username@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/fastqc_28926143.log ~/Downloads/
```
- `your-psc-username`: Replace with your actual username

Example:
```sh
 rsync -rltpDvp -e "ssh -l jparedesmontero" jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/fastqc_28926143.log ~/Downloads/```

### Send Files from Local Machine to HPC
```sh
rsync -avz /path/to/local/file username@hpc.example.edu:/path/to/remote/destination
```
Example:
```sh
rsync -avz project_data/ jorge@hpc.example.edu:/home/jorge/projects/
```

### Sync a Directory (Only Copy New/Modified Files)
```sh
rsync -avzu /local/directory/ username@hpc.example.edu:/remote/directory/
```
- `-u`: Skip files that are newer on the destination

### Delete Files on HPC that No Longer Exist Locally
```sh
rsync -avz --delete /local/directory/ username@hpc.example.edu:/remote/directory/
```

### Additional Options
- `-n` (Dry run): Preview changes without executing them
- `--progress`: Show real-time transfer progress
- `-e ssh`: Explicitly use SSH for the transfer

Example with progress:
```sh
rsync -avz --progress project_data/ jorge@hpc.example.edu:/home/jorge/projects/
```

## Troubleshooting
- If you get a "command not found" error, ensure `rsync` is properly installed.
- If connection issues arise, check SSH access:
  ```sh
  ssh username@hpc.example.edu
  ```
  If this fails, you may need to configure SSH keys or check network settings.
