---
title: backup
date: 2023-03-28
---

- The backup only covers `/e/arch/`

- Backups are cron-scheduled for Saturdays 04:00

- Backups are simple rsync copies, no versioning available (we simply lack the disk space for that)

You can influence what is backed up with three optional files:

- Backups are cron-scheduled for Sundays from 03:00 onwards

- If `/e/arch/users/[you]/SYNC_NO` is found, no rsync command will be run (think of this as an emergency brake if you just had a `rm -rf` incident)
- You can specify files to be included and/or excluded in `/e/arch/users/[you]/SYNC_INCLUDE` and/or `/e/arch/users/[you]/SYNC_EXCLUDE`. For the specifics, [see here](https://linux.die.net/man/1/rsync) under "Include/Exclude Pattern Rules".

- So far, `rsync` is run without `--delete-excluded`.

- The backup server would be very happy if you considered using especially the SYNC_EXCLUDE file to exclude non-essential (a) huge files (>100GB) and (b) folders with many small files. If you still want a backup of those many small files, consider zipping them.

- The actual command executed reads like this:

```
rsync -rlpt --delete --log-file=${logfile} ${include} ${exclude} errc1:/e/arch/users/${user} ${backup}
```

It very much depends on both ltsp01 and errc1 being up and running.

Examples:

- If you want to exclude a file `thing` from the backup, `SYNC_EXCLUDE` should read:

```thing```

- If `thing` is in `folder` stuff, you can be also specify

```stuff/thing```

because with the first version, other/stuff would be excluded as well (you can get fancy and use SYNC_INCLUDE to mitigate this).

- If you want to exclude all contents of folder (i.e. all folders called) stuff, SYNC_EXCLUDE should read:

```stuff/```

- The rsync "from" directory is errc1:/e/arch/users/[you], so if you want to exclude errc1:/e/arch/users/[you]/stuff, then specify either

```stuff/```

or

```[you]/stuff/```

Data safety:

- The log files are currently copied to /e/arch/users/[admin]/Backup-Logs. I'd be happy if you could check from time to time whether the log files correspond to what you did during the preceding week to make sure everything behaves as expected.

- If I understood correctly, you can use up to ~500GB on /home/moon/[you], and data put there will (officially) be backed up every night to the LRZ. So if you have important stuff, consider putting it there (as well).

Technicalities:

- Server: HP N54L, 4GB of ECC RAM, 4x 8TB HDD; OS: XigmaNAS

- The HDDs make up one ZFS Raid-Z0.

- The BTRFS on /e/arch uses compression (presumably zlib, unverified); compression levels seem to match the gzip-2 compression used on the backup server.

- The backup server’s (last known) IP is listed in /e/arch/users/[admin]/Backup-Logs/Nas-IP. If the IP changes, backups may fail due to IP restrictions for the ssh key.
