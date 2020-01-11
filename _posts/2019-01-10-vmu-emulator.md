---
title: "VMU DEAD: Inhabitable Spaces"
published: true
---

While transferring files from an old to a new computer I recently came across some of my very old projects. I recently wrote about my failed startup and some of the ways it shaped my perspective in [Media Purveyor: Lessons Learned]({% post_url 2019-01-06-media-purveyor %}). Now generally speaking, I am a very present and future oriented person. 

I am moved by the Tibetan sand mandala ritual in which monks spend days or weeks lovingly constructing a detailed representation of a mandala using colored sand. The mandala stands for a short period and then is ritualistically dismantled. This destruction of a thing of beauty, which required intense labor and care to create, depicts the impermanence of things. The relevant point is that, for me, this inspires a fruitful orientation towards activity: We need to care intensely and then let things go completely.

![Mandala](/assets/MandalaScaled.jpg)

 Perhaps it would have been less pompous to just include a photo of Elsa from Frozen but I couldn't find a photo labelled for re-use and so went with the Mandala thing. Anyhow, this entry will be my last backward-looking post of 2020. 

Home from college over a Christmas holiday, I happened upon on-line specifications for the VMU (Visual Memory Unit) of the Sega Dreamcast. The VMU is an insanely quirky idea from Sega: 
> What if we made our memory card for our console, itself, a console? Like... whoah.

I loved the trippy recursion of it. They gave the device a limited 48x32 pixel monochrome display thus requiring impressive ingenuity from game designers to rise to that challenge (everyone loves a challenge and underdog stories are often the most hope inspiring). In truth, I had been wanting to write an Atari 2600 emulator for months at that point but there were over a dozen Atari 2600 emulators available (even back then) and I didn't think I could bring anything new to the table. The VMU presented an opportunity and I could not believe my luck that someone had gone to such trouble to document so thoroughly. 

![VMU](/assets/VMUScaled.jpg){:style="float: right"} 

I was overcome with a manic energy the moment I realized it could be done. Over the next 70 hours I took three or four small naps but mostly survived on Mountain Dew and peanut butter crackers. The result of the frantic period of development was a full development platform VMU DEAD 
* (D)ebugger - Register, stack frame, and memory address inspection, conditional breakpoints which could be set either in the source assembly or at run-time (honestly the expression code was mostly copy-paste-modified from my recent compilers project), step into, step over call, etc.. I am pretty sure I even kept a buffer of the last 5 states so you could rewind a few steps earlier than your breakpoint. 
* (E)mulator - Different rendering modes, battery drain indicator (the microcontroller had low and high power draw modes), pause.
* (A)ssembler - Standard assembler with constants which could be used for "variables" (relative positions off the stack frame).
* (D)isassembler - In addition to disassembling instructions it would also insert comments for known patterns such as accessing interrupts or registers related to I/O. 

After sleeping for fourteen hours, I started to develop a small game for the VMU using the tool I had built. I loved that VMU DEAD was a completely _inhabitable space_. I could work _in_ this thing I had worked _on_. I've loved APIs, developer tools, and eDSLs ever since. 

I never published VMU DEAD on-line. Github did not exist and, even if it had, the raging inferiority complex I suffered back then would have made me too bashful. Both the source and the binaries are gone. So it goes.

In 2006 I decided to learn C# just in case I would eventually need it for a job (turns out I did). At the time I programmed professionally in Delphi (Object Pascal), x86 assembly, and occasionally C++. I was accustomed to manually managing memory, using pointers to iterate contiguous memory blocks, and using assembly when required for performance. This is embarassing now but at the time I didn't really believe that a garbage collected language could perform and I was pretty cranky about the idea of something else controlling memory. My experience of moving to a garbage collected language was somewhat like going from a manual to an automatic transmission: For weeks you suffer intermittent panic that there is something important you are forgetting to do. That sensation abates and eventually you even admit to yourself that seven out of ten times the automatic system does a better job than you could have done. 

In any event, I had lost the VMU DEAD source code but still had the trapper keeper where I had printed the VMU specifications (there were still a few peanut cracker crumbs). I thought that writing an emulator would be a good test of doing "low-level" stuff in .NET so I coded a quick emulator over a couple weekends [VMU Emulator](/assets/VMUEmulator.exe) (this requires Windows and an really old version of .NET). Below I have links to a few games that work with the emulator. Just download the game files into the same folder as the emulator executable. Sadly I did not write any of these but they are impressive representations of what can be done in 48x32 monochrome pixels (making much of little)
* [Pacman](/assets/PACMAN.VMS)
* [Tetris](/assets/TETRIS.VMS)
* [Slide Puzzle](/assets/SlidePuzzle.VMS)
* [4 Wins](/assets/4WINS.VMS)
* [Sketch](/assets/SKETCH.VMS)

At this point you may be thinking of how I started this post talking about my belief in the importance of letting things go so that we can move into the future. Then I tell you about how I re-wrote a subset of something I had done years before. Well then. I see. Erm. There are a few ways to look at it 
1. Perhaps we must let go so that we can progress into the future but sometimes life brings us back in a cyclical return (see Nietzsche's Eternal Return, Ka is a Wheel from "The Gunslinger", or any harvest based cosmology).
2. Sometimes what appears to be a return is really the helictical _progression_ of the dialectic synthesis a la Hegel.  
3. I am full of crap. 
