# pomod

This is a bash script that serves as a very basic pomodoro time tracker.

### Usage

```
./pomod
```

This script prints to STDERR the PID of itself. By using SIGHUP signal on the process, you can initialize the timer.

```
kill -s SIGHUP <pid>
```

The signal trigers timer to count down. Timer period can be set by `-t`/`--work-time` option (by default `1500` seconds, i.e. 25 minutes)

### Format

Once the `pomod` process receives the SIGHUP signal it prints out to STDOUT the timelog entry prefixed with exclamation (`!`).

After a period passed through another entry appears with a dot prefix (`.`).

Each entry can have a format manipulated with `-f`/`--entry-format` option (by default `%Y-%m-%dT%H:%M:%S`).
