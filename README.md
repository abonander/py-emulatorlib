py-emulatorlib
==============

A Python 3 wrapper for the telnet commands exposed by the Android emulator, py-emulatorlib facilitates easy development of scripted tests for functions that deal with telephony (calls, SMS, network state), location services (GPS), hardware events such as power state changes, and port redirection.

The commands this wrapper should implement are documented in the following Android Developer Guide:

http://developer.android.com/tools/devices/emulator.html#console

Not all commands are implemented yet. Contributions are certainly welcome.

The following commands are currently implemented:

* Telephony
  * Send/cancel/accept calls
  * Send SMS

Usage
=====

py-emulatorlib is very simple to use. It has no dependencies except the Python standard library. Simply copy *emulatorlib.py* to the directory of the script you want to use it in.

It is written for Python 3, but it will probably run fine in 2.7, or only require minor edits. I haven't tried.

It consists of a single class, Emulator, with a constructor that only requires the port number of the target emulator instance. The port number is displayed prominently in the emulator window's title bar.

![The title of the window is "5554:Jellyx86".](http://i.imgur.com/M4mVMBO.png?2)

For this emulator, the port is 5554. Now that we know this, we can access the emulator from Python like so:
```python

from emulatorlib import Emulator

# Constructor has an optional debug argument, pass true to get basic debug info.
emulator = Emulator(5554)

# Will send "Hello" to the emulator from 5556.
emulator.send_sms("5556", "Hello")

# Will initiate a call from 5556.
emulator.call("5556")

# Answer call from 5556
emulator.accept_call("5556")

# 5556 hang up
emulator.cancel_call("5556")

```

The phone number argument for the methods can be passed as a number or a string, but a string should be preferred since a phone number can consist of more than just digits.

The telnet session ends when the Python runtime exits. It does not need to be closed manually.

Contributing
============

The code style is simply Pythonic, as enumerated in [PEP8][1]. Indent with 4 spaces.

Code should be run through the [pep8][2] tool to verify compliance, but this is not required.

[1]: http://www.python.org/dev/peps/pep-0008/
[2]: https://pypi.python.org/pypi/pep8

License
=======

py-emulatorlib is licensed under the GNU General Public License (GPL), v2.
