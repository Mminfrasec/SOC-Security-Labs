# Linux Baseline — 2026-08-18

## Purpose

Assess my current ability to retrieve and explain previously studied Linux fundamentals without consulting notes.

## Conditions

- No notes used during the initial attempt.
- No Internet searches used during the initial attempt.
- No commands executed to verify answers during the initial attempt.
- Corrections will be performed only after completing the diagnostic.
- This baseline measures current retrieval ability, not professional competence.

## Results

| Topic | Status | Observed Gap | Next Action |
|---|---|---|---|
| Files and directories | Weak | Correctly distinguished a file from a directory at a basic level, but the explanation was limited and did not include filesystem behaviour or directory structure. | Reinforce the purpose of files and directories and practise creating, listing, navigating, copying, moving, and reading them. |
| Linux filesystem structure | Forgotten | Could not explain the Linux filesystem hierarchy, the meaning of `/`, or the purpose of directories such as `/home`, `/etc`, `/var`, and `/tmp`. `/` was incorrectly associated mainly with separation between directories rather than the filesystem root. | Rebuild the Linux filesystem hierarchy starting with `/` and the purpose of the main system directories. |
| Users and groups | Weak | Remembered the basic idea of a user but could not explain groups or their relationship to permissions and access control. | Review users, primary and secondary groups, UID, GID, and the relationship between identity and access. |
| Ownership | Forgotten | Could not explain file or directory ownership or the owner/group relationship. | Review owner and group ownership and inspect them using `ls -l`. |
| Permissions | Forgotten | Could not explain permission categories or the meaning of `r`, `w`, and `x`. | Learn owner, group, and others permissions and distinguish their behaviour on files and directories. |
| `chmod` and `chown` | Forgotten | Could not recall the purpose of either command. | Practise using `chmod` to modify permissions and `chown` to modify ownership in a controlled laboratory. |
| Processes | Forgotten | Could not explain what a process is. | Learn the basic process model and later practise identifying running processes. |
| Services and `systemctl` | Forgotten | Could not explain services and did not recall the purpose or use of `systemctl`. | Learn the relationship between services and processes and practise basic service inspection and control with `systemctl`. |
| Logs and `journalctl` | Forgotten | Confused a system log with a user login/session and could not recall where Linux logs are stored or how `journalctl` is used. | Rebuild the concept of system logging, review `/var/log`, and later practise inspecting journal entries with `journalctl`. |
| Network configuration | Forgotten | Could not recall how to inspect Linux IP or network-interface configuration. | Learn and practise basic Linux network inspection commands after core filesystem and permission fundamentals are recovered. |
| Connectivity testing | Retained | Correctly recalled that `ping` can be used with an IPv4 address to test network reachability. | Maintain through practical use and later reinforce the limitations of `ping`. |
| `sudo` and root | Weak | Remembered that `sudo` is related to elevated privileges but confused the command with the privileged account itself and could not explain the `root` user. | Distinguish a normal user, the `root` account, and temporary command execution with elevated privileges through `sudo`. |
| Package management | Forgotten | Could not recall package-management concepts or commands. | Introduce package installation, update, removal, and package information after the initial filesystem and permission block. |
| Backup and recovery | Retained | Correctly recalled the basic distinction between preserving copies of files or configurations and recovering them when required. | Reinforce through later practical backup and restore exercises. |

## Retained Knowledge

- Basic connectivity testing using `ping` with an IPv4 address.
- Basic purpose of backups as preserved copies of files or configurations.
- Basic purpose of recovery as restoring previously preserved information.

## Weak Knowledge

- Basic distinction between files and directories.
- Basic concept of a user.
- Relationship between `sudo` and elevated privileges.

## Forgotten Knowledge

- Linux filesystem hierarchy.
- Meaning of the filesystem root `/`.
- Purpose of `/home`, `/etc`, `/var`, and `/tmp`.
- Groups and their role in access control.
- File and directory ownership.
- Permission categories and `r`, `w`, and `x`.
- Purpose of `chmod` and `chown`.
- Processes.
- Services.
- `systemctl`.
- System logs.
- `/var/log`.
- `journalctl`.
- Linux network-configuration inspection.
- Package management.
- Role and capabilities of the `root` account.

## Priority for the Next Session

1. Rebuild the Linux filesystem model:
   - `/`
   - `/home`
   - `/etc`
   - `/var`
   - `/tmp`
   - Files and directories
   - Absolute and relative paths
2. Practise basic filesystem navigation and file operations.
3. Recover users and groups.
4. Recover ownership and permissions.
5. Distinguish normal users, `root`, and `sudo`.
6. Progress toward a controlled permissions laboratory only after these foundations are understood.

Processes, services, logging, network configuration, and package management should remain secondary until the filesystem, identity, ownership, and permissions model has been recovered.

## Limitations

This baseline measures unaided recall at a specific point in time. It does not demonstrate Linux administration competence.

The classifications represent retrieval demonstrated during this baseline only. A `Retained` result indicates successful basic recall of the concept tested and does not imply practical validation, reproduction, consolidation, or professional competence.

---

## Practical Evidence — 2026-08-18

This section records later practical evidence from the same date without changing the original unaided baseline results above.

### Conditions

- Ubuntu 26.04 was installed in a VMware virtual machine and used through the `student` account.
- The installation, system-update work, troubleshooting, and navigation practice were completed with step-by-step guidance.
- Terminal output was captured in screenshots.
- This was guided practice, not an independent reproduction or delayed retrieval test.

### Environment Validation

- Ubuntu booted successfully after installation.
- `uname -r` returned `7.0.0-30-generic` after reboot.
- `systemctl is-active open-vm-tools` returned `active`.
- Ubuntu repositories were reachable through the VMware NAT connection.
- An obsolete `file:///cdrom` APT source prevented a clean `apt update`.
- The source was located in `/etc/apt/sources.list.d/cdrom.sources` and disabled by moving it outside the active source directory.
- A later `apt update` completed without the CD-ROM repository error.
- Five desktop-related updates remained deferred through Ubuntu phased updates; they were not forced.

### Filesystem Navigation Evidence

The following commands or path forms were executed successfully during guided practice:

- `pwd` returned `/home/student` at the beginning and after returning home.
- `pwd` also verified `/var`, `/`, and `/home` during navigation.
- `ls` listed the contents of `/home/student`, `/var`, and `/etc`.
- `cd /` moved to the filesystem root.
- `cd /home`, `cd /etc`, and `cd /var` used valid absolute paths.
- `cd student` succeeded when the current directory was `/home`.
- `cd .` preserved the current directory.
- `cd ..` moved from `/home/student` to `/home`.
- `cd ~` returned to `/home/student`.

The following errors exposed unresolved gaps:

- `cd /descargas` failed because the path did not exist and did not match the case-sensitive home-directory entry `Descargas`.
- `cd /Descargas` failed because `/Descargas` was interpreted from filesystem root rather than from `/home/student`.
- `cd student` failed from `/var` and `/` because no relative `student` directory existed in those locations.
- `cd /student` failed because `/student` did not exist under filesystem root.
- Entering `/` and `/.` as commands produced `Es un directorio`, showing temporary confusion between a path and a command argument.

### Additional Guided Command Evidence

- `sudo apt update`, `apt list --upgradable`, and `sudo apt upgrade` were executed under guidance.
- `sudo mv` was used under guidance to disable the obsolete CD-ROM repository source.
- `grep` was used under guidance to locate the source containing `cdrom`.
- `sudo reboot` was executed before kernel and VMware Tools verification.
- `apt update` was initially repeated when `apt upgrade` was required; the distinction needed explicit correction.

### Updated Assessment After Guided Practice

| Topic | Updated Status | Evidence and Limitation |
|---|---|---|
| Basic navigation with `pwd`, `ls`, and `cd` | Guided practice — partial | Successful execution was observed across several directories, but path errors show that the mental model is not yet reliable. |
| Absolute and relative paths | Guided practice — weak | Valid absolute and relative paths were used, but root-relative paths, case sensitivity, and current-directory context caused repeated errors. |
| Linux filesystem structure | Partial practical exposure | `/`, `/home`, `/etc`, and `/var` were visited, but their purposes were not independently explained or retested. |
| Files and directories | Partial practical exposure | Directory contents were listed, but `mkdir`, `touch`, `cp`, `mv`, `cat`, `less`, and `ls -la` were not practised in this session. |
| `sudo` and root | Guided use only — concept remains weak | Commands were executed with `sudo`, but the distinction between the normal user, `root`, and temporary elevation was not independently explained. |
| Package management | Guided use only | Update and upgrade commands were executed, but the difference between them required correction and was not independently retested. |
| Services and `systemctl` | Single guided status check only | `open-vm-tools` was confirmed active, but service concepts and broader `systemctl` use remain unverified. |
| Troubleshooting | Guided remediation completed | The stale CD-ROM source was located and disabled, but the diagnosis and correction were not performed independently. |

### Next Evidence Required

1. Perform a delayed navigation retest without the original command sequence.
2. Explain why each tested absolute or relative path succeeds or fails.
3. Demonstrate case-sensitive path construction from both `/` and `/home/student`.
4. Practise `ls -la`, `mkdir`, `touch`, `cp`, `mv`, `cat`, and `less` in a safe directory.
5. Do not classify navigation as independently reproduced until the retest succeeds without guidance.
6. Continue afterward with users, groups, ownership, and permissions.

---

## Practical Evidence — 2026-08-20

This section records later study and practical evidence without changing the original unaided baseline results from `2026-08-18` or the guided evidence already recorded for that date.

### Conditions

- The initial retrieval attempt was completed before studying the filesystem and navigation block.
- Filesystem hierarchy, paths, navigation, and basic file operations were then studied with step-by-step guidance.
- The filesystem laboratory was completed inside `/home/student/linux-lab`.
- Terminal output was captured in a photograph.
- The final conceptual retrieval was completed without consulting notes.
- `cd ~`, `cd linux-lab`, and `pwd` were recalled and executed immediately without consulting the guide.
- `ls -la` required consultation of the guide and was then executed correctly.
- This session was not a delayed retrieval test or an independent reproduction of the complete laboratory.

### Initial Retrieval Before Study

The initial attempt showed partial recovery and several unresolved gaps:

- `/` was correctly identified as the filesystem root and as the separator between path components.
- A filesystem was incorrectly described as a system file.
- `/home`, `/var`, and `/tmp` were explained at a basic level.
- `/etc` was incorrectly described as containing system files and programs rather than primarily system and service configuration.
- The distinction between a file and a directory was incomplete.
- An absolute path was associated with being long or complete rather than being interpreted from `/`.
- A relative path was associated with being short rather than being interpreted from the current working directory.
- `.`, `..`, and `~` were not recalled.

After correction:

- `/tmp` was recognised as an absolute path because it begins at `/` and is interpreted from the filesystem root.
- `..` was correctly associated with the parent directory.
- `cd ~` was correctly associated with returning to the current user’s home directory.
- The difference between `/etc` and `/var` remained imprecise and required further correction.

### Guided Filesystem Practice

The supplied terminal evidence showed the following successful sequence:

```bash
pwd
cd ~
pwd
mkdir linux-lab
ls
cd linux-lab
pwd
mkdir documents
mkdir backups
ls
touch notes.txt
ls -la
cp notes.txt backups/notes-copy.txt
ls
ls backups
mv notes.txt documents/
ls
ls documents
ls backups
ls
```

The working paths and final structure were verified as:

```text
/home/student
/home/student/linux-lab

/home/student/linux-lab/
├── backups/
│   └── notes-copy.txt
└── documents/
    └── notes.txt
```

The terminal evidence demonstrated successful guided execution of:

- `pwd`
- `cd`
- `cd ~`
- `ls`
- `ls -la`
- `mkdir`
- `touch`
- `cp`
- `mv`

The following results were verified:

- `linux-lab` was created inside `/home/student`.
- `documents` and `backups` were created inside `linux-lab`.
- `notes.txt` was created in `linux-lab`.
- `cp notes.txt backups/notes-copy.txt` preserved the original and created the copy.
- `mv notes.txt documents/` removed the original from `linux-lab` and placed it inside `documents`.
- `ls documents` showed `notes.txt`.
- `ls backups` showed `notes-copy.txt`.
- No command error was visible in the supplied terminal evidence.

The explanation of the `cp` command initially identified the copy operation but used `/backups` imprecisely instead of the relative path `backups/notes-copy.txt`.

The explanation of the `mv` command correctly identified that `notes.txt` was moved from `linux-lab` into `documents`.

The exact source and destination arguments initially required correction:

```text
cp notes.txt backups/notes-copy.txt

Current working directory:
  /home/student/linux-lab

Relative source:
  notes.txt

Relative destination:
  backups/notes-copy.txt
```

```text
mv notes.txt documents/

Current working directory:
  /home/student/linux-lab

Relative source:
  notes.txt

Relative destination:
  documents/
```

The distinction between the following paths was recognised at a classification level, but the exact resolved locations required correction:

```text
documents/notes.txt
→ relative path
→ /home/student/linux-lab/documents/notes.txt
```

```text
/documents/notes.txt
→ absolute path
→ /documents/notes.txt
```

### Final Immediate Retrieval Without Notes

The following concepts were recalled correctly or at a sufficient basic level:

- `/` represents the filesystem root.
- `/` also separates components inside a path.
- `/home` normally contains users’ home directories.
- `/tmp` is used for temporary data.
- `/var` contains data that changes during system operation, although the explanation remained general.
- An absolute path begins at `/` and is interpreted from the filesystem root.
- A relative path is interpreted from the current working directory.
- `pwd` shows the current working directory.
- `ls` lists directory contents.
- `cd` changes the current working directory.
- `mkdir` creates a directory.
- `touch` creates an empty file when the file does not already exist.
- `cat` displays file content directly.
- `less` allows navigation through longer file content.

The following precision gaps remained:

- `/etc` was still described too generally as containing system and service files instead of primarily system and service configuration.
- The current working directory was confused with the `pwd` command that displays it.
- `.` was described as returning to the current directory instead of representing the current directory.
- `..` was described as performing movement instead of representing the parent directory.
- `~` was described as performing movement instead of representing the current user’s home directory.
- The distinction between `.`, `..`, and `~` and the commands `cd .`, `cd ..`, and `cd ~` remained imprecise.
- `ls -la` was correctly associated with hidden entries and executed successfully after consulting the guide, but its syntax was not retrieved independently and the detailed-listing purpose of `-l` was not initially stated.
- `cp` was described as copying files or directories without recalling that recursive directory copying normally requires `-r`.
- `mv` was recalled as moving files or directories, but its renaming function was not initially stated.
- The filesystem concept itself was incorrect during the initial retrieval and was not independently re-explained during the final retrieval.
- Independent execution of `cat` and `less` was not evidenced in the supplied terminal record.

### Immediate Retrieval With One Syntax Reference

The following commands were recalled and executed without consulting the guide immediately after study:

```bash
cd ~
cd linux-lab
pwd
```

The following command required consultation of the guide and was then executed successfully:

```bash
ls -la
```

This demonstrates successful immediate unaided retrieval and execution of the limited navigation sequence through `pwd`.

It also demonstrates successful reference-assisted execution of `ls -la`.

It does not demonstrate:

- Unaided retrieval of `ls -la`.
- Delayed retention.
- Independent reproduction of directory and file creation.
- Independent reproduction of copying or moving.
- Independent use of `cat` or `less`.
- Recovery of the complete filesystem model.
- Consolidation.

### Updated Assessment After Guided Practice

| Topic                                        | Updated Status                                     | Evidence and Limitation                                                                                                                                                       |
| -------------------------------------------- | -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Filesystem root `/`                          | Immediate retrieval successful                     | Correctly recalled as the filesystem root and as a path separator. Delayed retention remains untested.                                                                        |
| Main filesystem directories                  | Immediate retrieval — partial                      | `/home`, `/var`, and `/tmp` were explained at a basic level. `/etc` remained imprecise, and the filesystem concept itself was not independently re-explained correctly.       |
| Current working directory and `pwd`          | Immediate retrieval — weak                         | Correctly recalled that `pwd` shows the current location, but the directory itself was confused with the command that displays it.                                            |
| Absolute and relative paths                  | Guided practice and immediate retrieval — partial  | The basic distinction was recalled, but exact path resolution and the difference between `backups/` and `/backups/` required correction.                                      |
| `.`, `..`, and `~`                           | Immediate retrieval — partial                      | Their associated locations were recalled, but they were described as performing navigation rather than representing paths or locations used with commands such as `cd`.      |
| Basic navigation                             | Guided practice completed; limited immediate retrieval | `cd ~`, `cd linux-lab`, and `pwd` were recalled and executed without the guide. `ls -la` required consultation and was then executed correctly. Delayed retesting remains pending. |
| File and directory creation                  | Guided practice completed                          | `mkdir` and `touch` were executed successfully inside a controlled laboratory. Independent reproduction remains pending.                                                     |
| File copying and moving                      | Guided practice completed; explanation still weak  | `cp` and `mv` produced the expected results, but exact source and destination paths initially required correction. Recursive copying and renaming remain untested.             |
| `cat` and `less`                             | Basic purpose recalled; practical evidence limited | Their basic purposes were explained, but independent execution was not evidenced in the supplied terminal record.                                                            |
| Complete independent filesystem reproduction | Not tested                                         | The complete laboratory was not reproduced without the original guide.                                                                                                       |
| Delayed retention                            | Not tested                                         | The final retrieval occurred immediately after study.                                                                                                                        |
| Consolidation                                | Pending                                            | Guided success and immediate retrieval do not demonstrate consolidation.                                                                                                     |

### Next Evidence Required

1. Perform a delayed retrieval without reviewing the original explanations first.
2. Explain the filesystem concept independently.
3. Explain the precise purposes of `/home`, `/etc`, `/var`, and `/tmp`.
4. Distinguish the current working directory from the `pwd` command.
5. Explain `.`, `..`, and `~` as locations before explaining their use with `cd`.
6. Resolve absolute and relative paths from different stated working directories.
7. Retest `cd ~`, `cd linux-lab`, `pwd`, and `ls -la` without guidance.
8. Continue with users, groups, UID, GID, `root`, and `sudo` as scheduled.
9. Reproduce the complete filesystem and permissions laboratory later without the original guide.
10. Do not classify the filesystem block as `Recovered`, `Reproduced`, or `Consolidated` until delayed and independent evidence supports those states.
