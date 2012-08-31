# apply_corrections

A weechat plugin to re-print a user's messages with corrections applied when
they send a correction string (ex: s/typo/replacement).

## options

### check_every

Interval, in seconds, between each check for expired messages. If set to 0 no
check will be performed and all messages will be saved indefinitely.

### data_timeout

Time, in seconds, before a message is expired. If set to 0 messages will never
expire. This will most likely use a lot of memory.

### message_limit

Number of messages to store per nick. If set to 0 all messages will be saved
until they expire.

### print_format

Format string for the printed corrections (Default: "%(nick)s: %(corrected)s").
Variables allowed:

* nick:        The nick of the person who sent the messages.
* corrected:   The corrected text of the previous message(s).
* correction:  The correction (format: s/typo/replacement).
* original:    The original message before correction.
* pattern:     The "typo" portion of the correction.
* replacement: The "replacement" portion of the correction.
* timestamp:   The timestamp of the original message.

### print_limit

Maximum number of lines to correct and print to the buffer. If set to 0 all
lines that match the pattern will be printed.