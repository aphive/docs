## What is Cron?
Cron is a time based job scheduler in Unix-like Operating Systems. People who use and maintain software environments use cron to schedule jobs to run periodically at fixed times, dates, or intervals.

Cron is driven by a crontab (cron table) file that specifies shell commands to run periodically on the given schedules. Crontab files normally reside in the same location as the cron daemon. Individuaals can choose to have their own crontab files. These normally reside in the `/etc` directory.

## Crontab
A crontab file contains instructions for the cron daemon in the form of _"run this command at this time on this date"_. Each user has their own crontab, and commands in any given crontab will be executed as the user who owns the crontab.

### Crontab Layout
Each line of a crontab file represents a job, and looks like this:
```
+------------------- minute (0-59)
|  +---------------- hour (0-23)
|  |  +------------- day of month (1-31)
|  |  |  +---------- month (1-12)
|  |  |  |  +------- day of week (0-6) (Sunday to Saturday)
|  |  |  |  |
|  |  |  |  |
*  *  *  *  *  command_to_execute
```

### Expressions
| Field        | Required | Allowed Values | Allowed Special Characters |
|--------------|----------|----------------|----------------------------|
| Minutes      | Yes      | 0-50           | `*` , `,` , `-` |
| Hours        | Yes      | 0-23           | `*` , `,` , `-` |
| Day of Month | Yes      | 1-32           | `*` , `,` , `-` |
| Month        | Yes      | 1-12           | `*` , `,` , `-` |
| Day of Week  | Yes      | 0-6            | `*` , `,` , `-` |

#### Asterisk
The (`*`) character specifies all possible values for the field.

Example: `10 * 1 1 *` will run the command at minute 10 every hour on the first day in January or `at 2021-01-01 00:10:00`

#### Comma
The (`,`) character defines a list.

Example: `MON,WED,FRI` in the 5th field will tell the command to run on Mondays, Wednesdays and Fridays.

#### Round
The (`#`) pound character defines a comment.

Example: `# This command does something somewhere.`

#### Step Values
Step values can be used in conjunction with ranges. Following a range with `/<number>` specifies skips of the number's value through the range.

Example: `0-23/2` in the 2nd field denotes every other hour.

### Example Cron File
``` bash
# Run five minutes after midnight each day
5 0 * * * /path/to/script

# Run at 10pm on workdays and email John
0 22 * * 1-5 mail -s "Something Important" john

# Run this one as root
5 0 * * * root touch /tmp/file
```

## General Overview

### Cron basics
If this in your first time using cron, you will be prompted to choose an editor, the prompt will list your options and it will vary depending on which editor you have installed, for example:
```
no crontab for user - using an empty one

Select an editor. To change later, run 'select-editor'.
 1. /bin/nano <---- easiest
 2. /usr/bin/vim.basic
 3. /usr/bin/vim.tiny
 4. /bin/ed

 Choose 1-4 [1]:
```

### Remove all cron jobs for the current user
``` bash
crontab -r
```

### List the jobs for the current user
``` bash
crontab -l
```

### Edit your crontab file
``` bash
crontab -e
```

### Edit another user's cron jobs
```bash
crontab -u username -e
```

## Example crontab use

!!! important
    There is a difference between running a command every `x [window]` vs running a command every `x<sup>th</sup> [window]`.

    Example:  Every 15 minutes vs Every 15<sup>th</sup> minute.

### At minute 15
```
15 * * * * <command-to-execute>
```
Would Produce:
```
next at 2020-11-05 22:15:00
then at 2020-11-05 23:15:00
then at 2020-11-06 00:15:00
then at 2020-11-06 01:15:00
then at 2020-11-06 02:15:00
```

### At every 15<sup>th</sup> minute
```
*/15 * * * * <command-to-execute>
```
Would Produce:
```
next at 2020-11-05 21:30:00
then at 2020-11-05 21:45:00
then at 2020-11-05 22:00:00
then at 2020-11-05 22:15:00
then at 2020-11-05 22:30:00  
```

### At every minute
```
* * * * *  <command-to-execute>
```
Would Produce:
```
next at 2020-11-05 21:27:00
then at 2020-11-05 21:28:00
then at 2020-11-05 21:29:00
then at 2020-11-05 21:30:00
then at 2020-11-05 21:31:00  
```

### At every 5th minute
```
*/5 * * * * <command-to-execute>
```
Would Produce:
```
next at 2020-11-05 21:30:00
then at 2020-11-05 21:35:00
then at 2020-11-05 21:40:00
then at 2020-11-05 21:45:00
then at 2020-11-05 21:50:00  
```

### At minute 0, 5, and 10
```
0,5,10 * * * * <command-to-execute>
```
Would produce:
```
next at 2020-11-05 22:00:00
then at 2020-11-05 22:05:00
then at 2020-11-05 22:10:00
then at 2020-11-05 23:00:00
then at 2020-11-05 23:05:00
```

### At minute 0
```
0 * * * * <command-to-execute>
```
Would produce:
```
next at 2020-11-05 22:00:00
then at 2020-11-05 23:00:00
then at 2020-11-06 00:00:00
then at 2020-11-06 01:00:00
then at 2020-11-06 02:00:00
```

### At minute 0 past every 2<sup>nd</sup> hour
```
0 */2 * * * <command-to-execute>
```
Would produce:
```
next at 2020-11-05 22:00:00
then at 2020-11-06 00:00:00
then at 2020-11-06 02:00:00
then at 2020-11-06 04:00:00
then at 2020-11-06 06:00:00
```

### At minute 23 past every 2<sup>nd</sup> hour from 0 through 20
```
23 0-20/2 * * * <command-to-execute>
```
Would produce:
```
next at 2020-11-06 00:23:00
then at 2020-11-06 02:23:00
then at 2020-11-06 04:23:00
then at 2020-11-06 06:23:00
then at 2020-11-06 08:23:00
```

### At 00:00 on day-of-month 4 in January, April, July, and October.
```
0 0 4 1,4,7,10 * <command-to-execute>
```
Would produce:
```
next at 2021-01-04 00:00:00
then at 2021-04-04 00:00:00
then at 2021-07-04 00:00:00
then at 2021-10-04 00:00:00
then at 2022-01-04 00:00:00
```

### At 04:05 on Sunday
```
5 4 * * sun <command-to-execute>
```
Would produce:
```
next at 2020-11-08 04:05:00
then at 2020-11-15 04:05:00
then at 2020-11-22 04:05:00
then at 2020-11-29 04:05:00
then at 2020-01-05 04:05:00
```

### At 22:00 on every day-of-week from Monday through Friday.
```
0 22 * * 1-5 <command-to-execute>
```
Would produce:
```
next at 2020-11-05 22:00:00
then at 2020-11-06 22:00:00
then at 2020-11-09 22:00:00
then at 2020-11-10 22:00:00
then at 2020-11-11 22:00:00
```

### At minute 23 past every 2<sup>nd</sup> hour from 0 through 20
```
23 0-20/2 * * * <command-to-execute>
```
Would produce:
```
next at 2020-11-06 00:23:00
then at 2020-11-06 02:23:00
then at 2020-11-06 04:23:00
then at 2020-11-06 06:23:00
then at 2020-11-06 08:23:00
```

### At minute 0 past hour 0 and 12 on day-of-month 1 in every 2<sup>nd</sup> month.
```
0 0,12 1 */2 * <command-to-execute>
```
Would produce:
```
next at 2021-01-01 00:00:00
then at 2021-01-01 12:00:00
then at 2021-03-01 00:00:00
then at 2021-03-01 12:00:00
then at 2021-05-01 00:00:00
```

## Non Standards

### Yearly or At 00:00 on day-of-month 1 in January
```
@yearly <command-to-execute>
```
Would Produce:
```
next at 2021-01-01 00:00:00
then at 2022-01-01 00:00:00
then at 2023-01-01 00:00:00
then at 2024-01-01 00:00:00
then at 2025-01-01 00:00:00

```

### Monthly or At 00:00 on day-of-month 1
```
@monthly <command-to-execute>
```
Would Produce:
```
next at 2020-11-01 00:00:00
then at 2021-01-01 00:00:00
then at 2021-02-01 00:00:00
then at 2021-03-01 00:00:00
then at 2021-04-01 00:00:00
```

### Weekly or At 00:00 on Sunday
```
@weekly <command-to-execute>
```
Would Produce:
```
next at 2020-11-08 00:00:00
then at 2020-11-15 00:00:00
then at 2020-11-22 00:00:00
then at 2020-11-29 00:00:00
then at 2020-11-06 00:00:00

```

### Daily or At 00:00
```
@daily <command-to-execute>
```
Would Produce:
```
next at 2020-11-06 00:00:00
then at 2020-11-07 00:00:00
then at 2020-11-08 00:00:00
then at 2020-11-09 00:00:00
then at 2020-11-10 00:00:00

```

### Hourly or At minute 0
```
@hourly <command-to-execute>
```
Would Produce:
```
next at 2020-11-05 21:00:00
then at 2020-11-05 22:00:00
then at 2020-11-05 23:00:00
then at 2020-11-06 00:00:00
then at 2020-11-06 01:00:00

```

### After rebooting
```
@reboot <command-to-execute>
```
