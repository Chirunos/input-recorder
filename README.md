# input-recorder
GNU/Linux keyboard and mouse macro recorder.

What this is:
This is a quick hack or proof of concept to record and replay keyboard and mouse input in GNU/Linux. The whole program is just 263 lines of code, therefore it should be relatively easy to understand by anyone who wants to change it.

How is this different from other macro recorders:
- It requires root privileges, because it directly interacts with `/dev/input/event*`, files that are only readable by root.
- It monitors both mouse and keyboard. Many macro recorders only focus on keyboards.
- It accesses the Linux API directly and is written in a low-level language, being much faster than regular macro recorders that depend on several layers of software. You can even automate actions in 3rd person shooting games.
- It may not be accurate when replaying very precise macros and may get some timings wrong, due to being just a quick hack.
- Speed was the main motivation for writing this, there are many better macro tools for those who don't need speed.
- Difference from upstream: it allows the user to type while replaying a macro.

Improvement ideas that should all be quite easy to implement:
- Saving/loading from file
- Storing multiple macros at the same time
- Configurable keys and max size
- Adjusting repeat speed
- Repeating in loop

Installation (it is just a single file, just compile it): `$ gcc recorder.c -o recorder`

Starting: `# ./recorder`

Usage:
- Press F8 to start recording, F4 to end it
- After recording, press F7 to repeat recorded events. Press any key from keyboard to abort execution
- Press F9 to exit

Disclaimer:
As it is executed as a root, it has potential for causing direct harm or giving access to unauthorized people. Tested in Ubuntu 20.04 and openSUSE Leap 15.5, but I might test this in other distros upon need.
