# Using SCP to Transfer Files to and from the HPC

Secure Copy Protocol (`scp`) is a command-line tool for securely transferring files between a local machine and a remote HPC system.
---
## Transferring Files from HPC to Local Machine
To copy a file from the HPC to your local machine’s `Downloads` folder, use the following command:
```bash
scp your-username@data.bridges2.psc.edu:/ocean/projects/agr250001p/your-username/your-file-to-transfer C:\Users\your-local-computer-user\Downloads\ 
```
### Example
```bash
scp jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/fastqc.slurm C:\Users\jparedes\Downloads\
```
### Explanation:
- `scp` – Secure copy command.
- `jparedesmontero@data.bridges2.psc.edu:` – Your username and the remote server’s address.
- `/ocean/projects/agr250001p/jparedesmontero/fastqc.slurm` – The path to the file on the remote HPC system.
- `C:\Users\jparedes\Downloads\` – The destination directory on your local machine.
---
## Transferring Files from Local Machine to HPC
To copy a file from your local machine’s `Downloads` folder to the HPC system, use the following command:
```bash
scp C:\Users\your-local-computer-user\Downloads\your-file-to-transfer your-username@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/
```
### Example
```bash
scp C:\Users\jparedes\Downloads\installRsync jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/
```
### Explanation:
- `scp` – Secure copy command.
- `C:\Users\jparedes\Downloads\installRsync` – The file path on your local machine.
- `jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/` – The destination directory on the HPC system.

---

## Recursive Copying (Transferring Directories)

To copy an entire directory (folder) between systems, use the `-r` option:

- **From HPC to local:**
  ```bash
  scp -r jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/your-folder C:\Users\jparedes\Downloads\
  ```
- **From local to HPC:**
  ```bash
  scp -r C:\Users\jparedes\Downloads\your-folder jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/
  ```

## Transferring Large Files with Compression

To speed up the transfer of large files, you can use the `-C` option for compression:

```bash
scp -C -r your-username@data.bridges2.psc.edu:/ocean/projects/agr250001p/your-username/your-folder C:\Users\jparedes\Downloads\
```
Example
```bash
scp -C -r jparedesmontero@data.bridges2.psc.edu:/ocean/projects/agr250001p/jparedesmontero/snpcall C:\Users\jparedes\Downloads\
```
