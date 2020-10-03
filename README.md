# gf_backup_tool

This is a Backup utility aiming to backup the root directory.
It is made to do incremental backups to save space.

## installation

```bash
yay gf_backup_tool-git
```

## usage  
```bash
sudo backup_tool [option]
```

First usage only:
```bash
sudo backup_tool --init
```
Will:
-give you the possibility to change the amount of snapshots for dailly hourly mounthly weekly.
-give you the possibility to do a first backup manually.
-start systemd service so package checks every hours if a new snapshot is needed.

Every day usage:

```bash
sudo backup_tool --help
sudo backup_tool -h
```
displays the help message.

```bash
sudo backup_tool --list
```
lists every snapshots you have with tag. Tag can be D for dailly W for weekly (...) or C for your own.

```bash
sudo backup_tool --check
```
will check if a new snapshot is required accordingly to your settings. it is executed automaticly every hour by systemd service

```bash
sudo backup_tool --delete will promp you with the full snapshots list and give you the option to remove 1.
```

```bash
sudo backup_tool --show
```
displays user settings and exit.

```bash
sudo backup_tool --set [options]
```
change setting for max amount of snapshots. Examples:
```bash
sudo backup_tool --set Dailly=3 Weekly=2
```
or
```bash
sudo backup_tool --set Hourly=0
```

```bash
sudo backup_tool --create
```
will create a snapshot with the custom (C) flag.

```bash
sudo backup_tool --restore
```
will prompt the snapshots list (with tags) and let the user choice one to restore from.


## licence
[GPL](https://www.gnu.org/licenses/why-not-lgpl.html)
