---
title: "VMU DEAD: Inhabitable Spaces"
published: true
---

I recently came across some of my very old projects while transferring files from an old to a new computer. A few days ago I wrote about my startup and some of the ways it shaped my perspective on product development in [Media Purveyor: Lessons Learned]({% post_url 2019-01-06-media-purveyor %}). Today I want to share when I first fell in love with developer tooling, APIs, and IDEs (this is my last backward-looking post of 2020).

Home from college over a Christmas holiday, I happened upon on-line specifications for the VMU (Visual Memory Unit) of the Sega Dreamcast. The VMU is an insanely quirky idea from Sega: 
> What if we made our memory card for our console, itself, a console? Like... whoah.

I loved the trippy recursion of it. They gave the device a limited 48x32 pixel monochrome display thus requiring impressive ingenuity from game designers to rise to that challenge (everyone loves a challenge and underdog stories are often the most hope inspiring). In truth, I had been wanting to write an Atari 2600 emulator for months at that point but there were over a dozen Atari 2600 emulators available (even back then). I didn't think I could bring anything new to that particular table. On the other hand, the VMU presented an opportunity and I could not believe my luck that someone had gone to such trouble to document so thoroughly. 

![VMU](/assets/VMUScaled.jpg){:style="float: right"} 

I was overcome with a manic energy the moment I realized it could be done. Over the next 70 hours I took three or four small naps but mostly survived on Mountain Dew and peanut butter crackers. The result was more than an emulator. It was a fully operational development environment VMU DEAD 
* (D)ebugger - Register, stack frame, and memory address inspection, conditional breakpoints which could be set either in the source assembly or at run-time (honestly the expression code was mostly copy-paste-modified from my recent compilers project), step into, step over call, etc.. I am pretty sure I even kept a buffer of the last 5 states so you could rewind a few steps earlier than your breakpoint. 
* (E)mulator - Different rendering modes, battery drain indicator (the microcontroller had low and high power draw modes), pause.
* (A)ssembler - Standard assembler with constants which could be used for "variables" (relative positions off the stack frame).
* (D)isassembler - In addition to disassembling instructions it would also insert comments for known patterns such as accessing interrupts or registers related to I/O. 

After sleeping for fourteen hours, I started to develop a small game for the VMU using the tool I had built. I loved that VMU DEAD was a completely _inhabitable space_. I could work _in_ this thing I had worked _on_. This experience had a profound effect on my appreciation of and attitude towards APIs, developer tools, IDEs, and eDSLs. 

I never published VMU DEAD on-line. Github did not exist and, even if it had, the raging inferiority complex I suffered back then would have made me too bashful. Both the source and the binaries are gone. So it goes. The code is unlikely to have won any awards anyway. 

In 2006 I decided to learn C# just in case I would eventually need it for a job (turns out I did). At the time I programmed professionally in Delphi (Object Pascal), x86 assembly, and occasionally C++. I was accustomed to manually managing memory, using pointers to iterate contiguous memory blocks, and using assembly when required for performance. This is embarassing now but at the time I didn't really believe that a garbage collected language could perform and I was pretty cranky about the idea of something else controlling memory. My experience of moving to a garbage collected language was somewhat like going from a manual to an automatic transmission: For weeks, you suffer intermittent panic that there is something important you are forgetting to do. That sensation abates and eventually you even admit to yourself that seven out of ten times the automatic system does a better job than you could have done. 

In any event, I had lost the VMU DEAD source code but still had the binder where I had printed the VMU specifications (with a few stray peanut butter cracker crumbs as evidence of my prior crazed development). I thought that writing an emulator would be a good test of doing "low-level" stuff in .NET so I coded a quick emulator over a couple weekends. 
* [Download VMU Emulator](/assets/VMUEmulator.exe) (this requires Windows and an really old version of .NET). 
* Links to a few games that work with the emulator. 
    * [Pacman](/assets/PACMAN.VMS)
    * [Tetris](/assets/TETRIS.VMS)
    * [Slide Puzzle](/assets/SlidePuzzle.VMS)
    * [4 Wins](/assets/4WINS.VMS)
    * [Sketch](/assets/SKETCH.VMS)

Just download the game files into the same folder as the emulator executable. Sadly, I did not write any of these but they are impressive representations of what can be done by creative software developers with only 48x32 monochrome pixels. The VMU was a small space but VMU DEAD was the first significant inhabitable space that I created. 


