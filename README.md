**remind-email** is a tool to send reminds produced by [remind](https://dianne.skoll.ca/projects/remind) command via email.

### How to use
First of all you need to setup SMTP and some other configurations using
configuration file. See `remind-email.conf` file in the current source
distribution as an example. `remind-email` expects the file is to be located at
`~/.config/remind-email/remind-email.conf`. This behavior can be changed using
`-c` command-line option.

Next step is to create reminder file(s) in `~/.config/remind-email/reminds`
folder. Files location can be changed using `-r` command-line option. Multiple
files are supported.

Typical scenario is to use `cron` to call `remind-email` once per day (e.g. at
midnight) to send an email with reminds for the upcoming day.

### Examples
Send a reminder email every midnight.
```
01 0 * * *    user    /usr/bin/remind-email -c /home/user/.config/remind-email/remind-email.conf -r /home/user/.config/remind-email/reminds
```
