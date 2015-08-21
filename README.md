ZModem integration for iTerm 2
------------------------------

This script can be used to automate ZModem transfers from your OSX desktop to a server that can run lrzsz (in theory, any machine 
that supports SSH), and vice-versa.

The minimum supported iTerm2 version is 1.0.0.20120108

Setup is pretty simple:

0. Install lrzsz on OSX: brew install lrzsz
1. Save the iterm2-send-zmodem.sh and iterm2-recv-zmodem.sh scripts in /usr/local/bin/
2. Set up Triggers in iTerm 2 like so:

<pre>
    Regular expression: rz waiting to receive.\*\*B0100
    Action: Run Silent Coprocess
    Parameters: /usr/local/bin/iterm2-send-zmodem.sh

    Regular expression: \*\*B00000000000000
    Action: Run Silent Coprocess
    Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
</pre>

To send a file to a remote machine:

1. Type "rz" on the remote machine
2. Select the file(s) on the local machine to send
3. Wait for the coprocess indicator to disappear

The receive a file from a remote machine

1. Type "sz filename1 filename2 … filenameN" on the remote machine
2. Select the folder to receive to on the local machine
3. Wait for the coprocess indicator to disappear

Future plans (patches welcome)

 - Visual progress bar indicator
