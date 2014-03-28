electric-fence
==============
This is Electric Fence 2.2 — 25-Sep-2014

Electric Fence is a different kind of malloc() debugger. It uses the virtual
memory hardware of your system to detect when software overruns the boundaries
of a malloc() buffer. It will also detect any accesses of memory that has
been released by free(). Because it uses the VM hardware for detection,
Electric Fence stops your program on the first instruction that causes
a bounds violation. It's then trivial to use a debugger to display the
offending statement.

This version will run on:

	BSD and OS/X

	Linux kernel version 1.1.83 and above. Earlier kernels have problems
	with the memory protection implementation.

	All System V Revision 4 platforms (and possibly earlier revisions)
	including:
		Every 386 System V I've heard of.
		Solaris 2.x
		SGI IRIX 5.0 (but not 4.x)

	IBM AIX on the RS/6000.

	SunOS 4.X (using an ANSI C compiler and probably static linking).

	HP/UX 9.01, and possibly earlier versions.

	OSF 1.3 (and possibly earlier versions) on a DECalpha.

On some of these platforms, you'll have to uncomment lines in the Makefile
that apply to your particular system, though it would be better if someone
added a better build-system so that this was not necessary.

If you test Electric Fence on a platform not mentioned here, please send me a
report.

It will probably port to any ANSI/POSIX system that provides mmap(), and
mprotect(), as long as mprotect() has the capability to turn off all access
to a memory page, and mmap() can use /dev/zero or the MAP_ANONYMOUS flag
to create virtual memory pages.

Complete information on the use of Electric Fence is in the manual page
libefence.3 .  You can read it with "man ./libefence.3".
