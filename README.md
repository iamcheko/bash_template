# bash-template

This script is a refactoring of my old ksh-template script. Since most of the Unix systems this days
do have a bash shell available.

This is a simple born again shell template with logging mechanism and builtin logrotation. All commands 
that are defined between CMD_START and CMD_END, will be checked in two ways. First it will verify,
that the command exists and it is executable. Second it also checks the body if all CMD_* variables
are defined.

This script comes with a config file, which is found in the etc folder. This config file is sourced
and not parsed, so you have to take care who has write permission to this file, since all code that
is in this file gets executed.

This script takes care of the Unix "standard" directory structure. That means that you have to put
it in a bin directory. It will find its config file in ../etc and create a logfile in ../var/log. If 
the ../var/log folder does not exist, it will create it.

## Usage

The script commes with a build in help function.
``` bash
$ bin/bash-template -h
bash-template [ -hv ]
-h       print this help message
-v       print messages to standard out
```

Or run it straight away with verbose output.
``` bash
$ bin/bash-template -v
2019-07-07 21:33:54 INFO - Variable CMD_DATE on line 39 has been initialized to /bin/date
2019-07-07 21:33:54 INFO - Variable CMD_LOGGER on line 40 has been initialized to /usr/bin/logger
2019-07-07 21:33:54 INFO - Variable CMD_MKDIR on line 41 has been initialized to /bin/mkdir
2019-07-07 21:33:54 INFO - Variable CMD_MV on line 42 has been initialized to /bin/mv
2019-07-07 21:33:54 INFO - Variable CMD_RM on line 43 has been initialized to /bin/rm
2019-07-07 21:33:54 INFO - Variable CMD_STAT on line 44 has been initialized to /usr/bin/stat
2019-07-07 21:33:54 INFO - Variable $CMD_MKDIR on line 116 is set to /bin/mkdir
2019-07-07 21:33:54 INFO - Variable $CMD_MKDIR on line 118 is set to /bin/mkdir
2019-07-07 21:33:54 INFO - Variable $CMD_DATE on line 143 is set to /bin/date
2019-07-07 21:33:54 INFO - Variable $CMD_LOGGER on line 157 is set to /usr/bin/logger
2019-07-07 21:33:54 INFO - Variable $CMD_LOGGER on line 161 is set to /usr/bin/logger
2019-07-07 21:33:54 INFO - Variable $CMD_LOGGER on line 165 is set to /usr/bin/logger
2019-07-07 21:33:54 INFO - Variable $CMD_RM on line 288 is set to /bin/rm
2019-07-07 21:33:54 INFO - Variable $CMD_MV on line 300 is set to /bin/mv
2019-07-07 21:33:54 INFO - Variable $CMD_STAT on line 330 is set to /usr/bin/stat
2019-07-07 21:33:54 INFO - Variable $CMD_STAT on line 332 is set to /usr/bin/stat
Hallo Welt :D
```

Or without
``` bash
$ bin/bash-template
Hallo Welt :D
```




