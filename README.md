# 52
A quick day statistics script.

## Idea
This script creates a list of activities, chosen by you, each day to fill out, for example whether you read, did sports, how many glasses of water you drank or at what hour you woke up. For each day, a file with the date in ISO format (YYYY-MM-DD) is kept at a chosen journal_path. In the end, you can use other tools like `grep`, or `wc` to review your year's stats.

## Usage
```sh
52 foo              # Add foo as an activity you did today
52 foo bar          # Add the key foo with the value bar to today's stats
52 -d foo           # Delete the foo key from today's stats
52 -c [COMMENT]     # Add a comment for today

52 -t [DATE]        # Print [DATE]'s stats (or today's if no [DATE] supplied)
52 -e [DATE]        # Edit [DATE]'s stats (or today's if no [DATE] supplied)

52 -u               # Undo the latest change
52 -T               # Edit the template
```

## Configuration
Edit the `EDITOR` and `JOURNAL_PATH` variables in the script. Move the script to your `$PATH`. Call `52 -T` to edit the template. This is what it could look like:

```
woke-up ??
read ??
youtube ??
outside ??
social ??
uni ??
program ??
gym ??
movie ??
languages ??
```

## Example commands for using the data
Every day you read.

```sh
grep -rl "read" ~/journal
```

The number of days you went to uni.

```
grep -rl "uni" ~/journal | wc -l
```

Every day you either went outside or hung out.

```
grep -rlE "outside|social" ~/journal
```
