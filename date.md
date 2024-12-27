# date command

## Overview

### Basic usage, current timezone
```
$ date
Wed Dec 25 11:20:07 IST 2024
```

### UTC date
```
$ date -u
Wed Dec 25 05:50:45 UTC 2024
```

### Format
* -I[FMT], --iso-8601[=FMT]  output date/time in ISO 8601 format.
                               FMT='date' for date only (the default),
                               'hours', 'minutes', 'seconds', or 'ns'
```
$ date -I
2024-12-25

$ date -Iseconds
2024-12-25T11:23:52+05:30

$ date -Iseconds -u
2024-12-25T05:54:39+00:00

$ date "+%Y-%m-%d %H:%m:%S.%N"
2024-12-25 11:12:55.969285700

$ date -u "+%Y-%m-%d %H:%m:%S.%N"
2024-12-25 05:12:00.998186800
```
### Print seconds since epoch
* Note that the seconds currently are around 1.7 billion (i.e. 10 digits)
```
$ date +%s
1735271299
```



