^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package serial
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Forthcoming
-----------
* Build tests on Travis.
* Add unix timer tests, clarify tests are only on unix at present, move test builds into separate makefile.
* Pre-fill buffer at start of read, to avoid the select if unnecessary.
* Wrap nanoseconds when >= 1e9, rather than > 1e9.
* Fix for computing an expiry without rollover.
* Divide by 1e9 to get seconds from nanoseconds, instead of 1e6.
* use static casts rather than C-style casting
  C-style casting can result in undesired reinterpret_casts
  So we should avoid them, see:
  http://stackoverflow.com/questions/332030/when-should-static-cast-dynamic-cast-and-reinterpret-cast-be-used
* Contributors: Christopher Baker, Mike Purvis, Nicolas Bigaouette, William Woodall

1.1.6 (2013-10-17)
------------------
* Move stopbits_one_point_five to the end of the enum, so that it doesn't alias with stopbits_two.

1.1.5 (2013-09-23)
------------------
* Fix license labeling, I put BSD, but the license has always been MIT...
* Added Microsoft Visual Studio 2010 project to make compiling on Windows easier.
* Implemented Serial::available() for Windows
* Update how custom baudrates are handled on OS X
  This is taken from the example serial program on Apple's developer website, see:
  http://free-pascal-general.1045716.n5.nabble.com/Non-standard-baud-rates-in-OS-X-IOSSIOSPEED-IOCTL-td4699923.html
* Timout settings are now applied by reconfigurePort
* Pass LPCWSTR to CreateFile in Windows impl
* Use wstring for ``port_`` type in Windows impl

1.1.4 (2013-06-12 00:13:18 -0600)
---------------------------------
* Timing calculation fix for read and write.
  Fixes `#27 <https://github.com/wjwwood/serial/issues/27>`_
* Update list of exceptions thrown from constructor.
* fix, by Thomas Hoppe <thomas.hoppe@cesys.com>
  For SerialException's:
  * The name was misspelled...
  * Use std::string's for error messages to prevent corruption of messages on some platforms
* alloca.h does not exist on OpenBSD either.

1.1.3 (2013-01-09 10:54:34 -0800)
---------------------------------
* Install headers

1.1.2 (2012-12-14 14:08:55 -0800)
---------------------------------
* Fix buildtool depends

1.1.1 (2012-12-03)
------------------
* Removed rt linking on OS X. Fixes `#24 <https://github.com/wjwwood/serial/issues/24>`_.

1.1.0 (2012-10-24)
------------------
* Previous history is unstructured and therefore has been truncated. See the commit messages for more info.
