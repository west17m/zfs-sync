# zfs-sync

This is a wrapper for the zfs send/receive combination of commands.  The goal is to allow a single cron command to perform full and incremental backups of one or more local zfs filesystems to one or more remote servers.  I use http://www.funtoo.org/Keychain to help with remote authenication.

## Usage

LOG_LEVEL=[0-7] zfs-sync LOCAL_ZFS REMOTE_URI_LOGIN REMOTE_ZFS

## Example
zfs-sync "tank/home" "backup@server2.tld.com" "tank/backup/server1.tld.com"

The above will snapshot and send the contents of server1.tld.com's tank/home filesystem to server2.tld.com.  On the first run, it will be the entire snapshot.  On subsequent runs, it will be only the changes.

## Log levels

 * 0 - emergency
 * 1 - alert
 * 2 - critical
 * 3 - error
 * 4 - warning
 * 5 - notice
 * 6 - info (default)
 * 7 - debug
