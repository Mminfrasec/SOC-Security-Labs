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
