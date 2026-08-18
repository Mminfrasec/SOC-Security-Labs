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
