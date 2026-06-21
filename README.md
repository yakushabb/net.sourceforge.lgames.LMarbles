# LMarbles

___A flatpak package for LMarbles___

### Errors

```
gdb /app/bin/lmarbles 
GNU gdb (GDB) 17.2
Copyright (C) 2025 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-unknown-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from /app/bin/lmarbles...
Reading symbols from /usr/lib/debug/app/bin/lmarbles.debug...
(gdb) run
Starting program: /app/bin/lmarbles 

This GDB supports auto-downloading debuginfo from the following URLs:
  <ima:enforcing>
  <https://debuginfod.fedoraproject.org/>
  <ima:ignore>
Enable debuginfod for this session? (y or [n]) y
Debuginfod has been enabled.
To make this setting permanent, add 'set debuginfod enabled on' to .gdbinit.
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/usr/lib/x86_64-linux-gnu/libthread_db.so.1".
[New Thread 0x7ffff5b206c0 (LWP 16)]
[New Thread 0x7ffff531f6c0 (LWP 17)]
[New Thread 0x7ffff4b1e6c0 (LWP 18)]
[New Thread 0x7fffeffff6c0 (LWP 19)]
[New Thread 0x7fffef3ff6c0 (LWP 20)]
[Thread 0x7fffef3ff6c0 (LWP 20) exited]
[New Thread 0x7fffef3ff6c0 (LWP 21)]
[New Thread 0x7fffeead26c0 (LWP 22)]
[New Thread 0x7fffed3ff6c0 (LWP 23)]
[New Thread 0x7fffecbfe6c0 (LWP 24)]
[New Thread 0x7fffbffff6c0 (LWP 25)]
[New Thread 0x7fffbf7fe6c0 (LWP 26)]
loading configuration /home/sabri/.lmarbles/lmarbles.conf
loading profile /home/sabri/.lmarbles/lmarbles.prf
searching for level sets...
  Original
[New Thread 0x7fffbeffd6c0 (LWP 27)]
loading levelsets...
Original... ok
loading graphics sets...
'metal'... 
ok
'stone'... 
ok
'wood'... 
ok

Thread 1 "lmarbles" received signal SIGSEGV, Segmentation fault.
0x00007ffff7917d3f in Blit8888to8888PixelSwizzleAVX2 () from /usr/lib/x86_64-linux-gnu/libSDL3.so.0
(gdb) bt full
#0  0x00007ffff7917d3f in Blit8888to8888PixelSwizzleAVX2 () at /usr/lib/x86_64-linux-gnu/libSDL3.so.0
#1  0x00007ffff78fe942 in SDL_SoftBlit () at /usr/lib/x86_64-linux-gnu/libSDL3.so.0
#2  0x00007ffff7bc20a3 in SDL_LowerBlit_REAL () at /usr/lib/x86_64-linux-gnu/libSDL2-2.0.so.0
#3  0x00007ffff7bc225d in SDL_UpperBlit_REAL () at /usr/lib/x86_64-linux-gnu/libSDL2-2.0.so.0
#4  0x00007ffff7f1dead in SDL_UpdateRects (surface12=<optimized out>, numrects=<optimized out>, rects12=<optimized out>) at /run/build/sdl12-compat/src/SDL12_compat.c:7513
        dstrect20 = {x = 0, y = 0, w = 640, h = 480}
        upload_later = <optimized out>
        logicalPal = <optimized out>
        whole_screen = SDL_TRUE
        renderer = <optimized out>
        rect20 = {x = 0, y = 0, w = 640, h = 480}
        j = <optimized out>
        pixsize = <optimized out>
        srcpitch = <optimized out>
        pixels = 0x7fffc673f010
        pitch = 2048
        i = 0
        ThisIsSetVideoModeThread = <optimized out>
#5  0x00007ffff7f1e1d8 in SDL_UpdateRect (screen12=<optimized out>, x=x@entry=0, y=y@entry=0, w=w@entry=0, h=h@entry=0) at /run/build/sdl12-compat/src/SDL12_compat.c:7564
        rect12 = {x = 0, y = 0, w = 640, h = 480}
#6  0x0000555555565ebd in Sdl_FUpd () at sdl.c:458
#7  Sdl_UnDim (steps=<optimized out>, delay=20, trp=<optimized out>) at sdl.c:554
        buffer = 0x5555558fdae0
        per_step = <optimized out>
        i = 255
#8  0x000055555556198a in L_Ini (c=c@entry=0, l=l@entry=0) at levels.c:604
        nm = <optimized out>
        e = <optimized out>
        gst_ok = <optimized out>
        px = <optimized out>
        py = <optimized out>
        i = <optimized out>
        j = <optimized out>
        k = <optimized out>
        lp = <optimized out>
        str = "0,0%\000\177\000\000\027\232\273\367\377\177\000\000\360\326\377\377\377\177\000\000\300%\207\367\377\177\000\000\360\326\377\377\377\177\000\000\006\262\274\367\377\177\000\000\360\326\377\377\377\177\000\000\264\370\217UUU\000"
--Type <RET> for more, q to quit, c to continue without paging--
        off = <optimized out>
        str_num = {0x5555555681d9 "1.", 0x5555555681dc "2.", 0x5555555681df "3.", 0x5555555681e2 "4.", 0x5555555681e5 "5.", 0x5555555681e8 "6.", 0x5555555681eb "7.", 0x5555555681ee "8.", 0x5555555681f1 "9.", 0x5555555681f4 "10."}
#9  0x000055555555ab1f in G_Opn () at game.c:419
        flgs = <optimized out>
#10 0x0000555555556c63 in main (argc=<optimized out>, argv=<optimized out>) at main.c:272
        e = {type = 2 '\002', active = {type = 2 '\002', gain = 0 '\000', state = 1 '\001'}, key = {type = 2 '\002', which = 0 '\000', state = 1 '\001', keysym = {scancode = 36 '$', sym = SDLK_RETURN, mod = KMOD_NONE, unicode = 13}}, motion = {type = 2 '\002', which = 0 '\000', state = 1 '\001', x = 36, y = 0, xrel = 13, yrel = 0}, button = {type = 2 '\002', which = 0 '\000', button = 1 '\001', state = 0 '\000', x = 36, y = 0}, jaxis = {type = 2 '\002', which = 0 '\000', axis = 1 '\001', value = 36}, jball = {type = 2 '\002', which = 0 '\000', ball = 1 '\001', xrel = 36, yrel = 0}, jhat = {type = 2 '\002', which = 0 '\000', hat = 1 '\001', value = 0 '\000'}, jbutton = {type = 2 '\002', which = 0 '\000', button = 1 '\001', state = 0 '\000'}, resize = {type = 2 '\002', w = 36, h = 13}, expose = {type = 2 '\002'}, quit = {type = 2 '\002'}, user = {type = 2 '\002', code = 36, data1 = 0xd, data2 = 0xd}, syswm = {type = 2 '\002', msg = 0xd}}
        go_on = 1
        ms = <optimized out>
        aux = "LMarbles 1.1.1\000\000\006\000\000\000\214\000\000\000\346\354\377\377\377\177\000\000f+\377\367\377\177", '\000' <repeats 25 times>


```
