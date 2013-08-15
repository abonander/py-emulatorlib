py-emulatorlib
==============

A Python 3 wrapper for the telnet commands exposed by the Android emulator, py-emulatorlib facilitates easy development of scripted tests for functions that deal with telephony (calls, SMS, network state), location services (GPS), hardware events such as battery levels, and port redirection.

The commands this wrapper should implement are documented in the following Android Developer Guide:

http://developer.android.com/tools/devices/emulator.html#console

Not all commands are implemented yet. Contributions are certainly welcome.

The following commands are currently implemented:

* Telephony
  * Send/cancel/accept calls
  * Send SMS

py-emulatorlib is licensed under the GNU General Public License (GPL), v2.
