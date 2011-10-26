ZModem integration for iTerm 2
------------------------------

This script can be used to automate ZModem transfers from your OSX desktop to a server that can run lrzsz (in theory, any machine 
that supports SSH), and vice-versa.

Setup is pretty simple:

1) Save the iterm2-send-zmodem.sh and iterm2-recv-zmodem.sh scripts in /usr/local/bin/

2) Set up a Trigger in iTerm 2 like so:

Build newer than 1.0.0.20111026

    Regular expression: \*\*B0100
    Action: Run Coprocess
    Parameters: /usr/local/bin/iterm2-send-zmodem.sh

    Regular expression: \*\*B00000000000000
    Action: Run Coprocess
    Parameters: /usr/local/bin/iterm2-recv-zmodem.sh

Build older than 1.0.0.20111026 (only receive supported)

    Regular expression: [\$#] rz( -v)?$
    Action: Run Coprocess
    Parameters: /usr/local/bin/iterm2-send-zmodem.sh

