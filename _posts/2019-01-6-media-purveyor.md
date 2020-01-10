---
title: "Media Purveyor: Lessons Learned "
published: true
---

# History
From some forgotten month in 2004 to March of 2006, I spent spare hours developing a media management application with a number of novel features. Convinced this innovation must equate to financial success, I left a salaried position to work full-time developing the product I thought would become a household name.

The first problem encountered on the road to making the product a household name was the name itself: **Media Purveyor**

Yikes! As a name "Media Purveyor" _fails_ to be unique, exciting, or informative but _excels_ at conveying an odd combination of 
boring, pompous, and vaguely creepy. I wish I could remember what I was thinking but I doubt I was thinking anything at all (an absence of any thinking is probably the most pervasive thinking error). I was an "engineer" and thought the name unimportant. Didn't the The Bard have Juliet say "That which we call a rose By any other name would smell as sweet"? Perhaps. Even still, no one will buy roses labelled "Squelchy Stink Blooms". 

During the process of developing the product I learned many other valuable lessons but these lessons were not learned sufficiently early to save the venture. I ran out of my own money (never solicited VC) and returned to collecting a paycheck solving problems for other people who had done the hard work of finding paying customers and inventing good names. 

A few days ago I found a copy of the Media Purveyor v2.9 installer (v3.4 or so was the last version) and decided to fire it up on my Windows 10 computer. I was shocked by many things. If you have a Windows OS I invite you to give it a try: [Media Purveyor v2.9 Download](/assets/MediaPurveyorSetup29.exe) (**NOTE** The uninstaller does work.)

First, I was shocked the application worked on a modern OS in 2020. Well mostly worked. One dialog popped under the window rather than over. Also the application threw an error on exiting.

Second, I was impressed by how much is comically and avoidably wrong with the user experience. We'll start with the hyper-animated title screen: You cannot tell from the static image but trust me when I tell you the water is... um... undulating is probably the word. Inside the transparent sphere you will spot small red, green, and blue spheres. These three orbs both spin and move in and out like a nauseating carnival amusement. Why are they doing that? I don't know. I coded the effects but I honestly don't know why. I do know that you score in the 90th percentile for stomach constitution if you can stare at this screen for longer than 45 seconds without losing your last meal. 

![Title Screen](/assets/MediaPurveyorTitleScreen.jpg){:max-width="100%"}

We move on to considering the main media browser screen. The image is scaled so it might be hard to tell but there are between 11 and 14 bazillion indicators, widgets, doodads, and things to press, click, slide, and twist. Almost every single surface can be right-clicked to reveal a dizzying array of additional options. Hovering over almost anything brings up a tooltip which is closer to a tool-novella. Furthermore, the area on the left can be configured to show even more stuff; most things default to hidden. So this sensory overload nightmare was my idea of restraint. It is a kitchen sink interface with no sense of priority, proportion, weight, balance or flow. 

![Media Browser](/assets/MediaPurveyorBrowserScaled.jpg){:max-width="100%"}

That leads to the third major shock. I was proud of how much functionality had been built in the roughly 2,300 hours spent on development (another 700 hours were spent on marketing, help system / training materials, and customer support). 
* Image Editor with 43 effects, _layers_, varying selection techniques, wizards, and more; all coded from the ground up based on research.
* Completely custom widget set built for this application with layout managers, custom styling, and effects.
* Browser with multi-threaded thumbnail loading (so the CPU could decode one while waiting on the I/O for another).
* Plugin based architecture for image editing effects, media decoders, encoders, metadata readers, etc..
* Slideshow
* File (en/de)cryption and filename obfuscation (creepy feature added because a co-worker suggested it)
* A dozen batch processing features.
* Even a feature that would publish images to an indexed and searchable on-line gallery using static JSON files for the indices and an AJAX client to perform the search.

The funny thing? Remember when I claimed the application had some novel features that set it apart? Well none of the functionality listed above is it! 

Media Purveyor (ugh that name!) had one neat trick: it could read/write metadata from/to many different types of files without otherwise impacting the file contents. So what? Well with that one trick it could provide
* Lossless Image Editing. The application could store multiple "views" of an image inside the source image file without having to re-encode the image (which for many formats is lossy). 
  * For example, you might take one very nice photo and create a view that crops the image one way and applies a blur. 
  * Another view may crop a different region and apply a sepia filter. 
  * A third view might apply an oil painting effect. 
  * Ultimately that one file would contain the original plus three views. Since the information is stored inside the file it was entirely portable and moves with the media file as it travels from one device to the next.
* Portable keyword tagging and search. Keywords can be added to images and videos to support cross-cutting concern based searching. Rather than organizing media into artificial taxonomies / hierarchies, a media managers (marketing for example) can  search an enormous catalog of media based on the Venn intersection of needs. 
* Portable Schema-Less Data Entry. In addition to keywords, media can be described using user defined "Entry Screens". Each media file tagged with an entry screen contains enough of the schema of that entry screen to enable another client to also edit and search using that Entry Screen. 

The value proposition was portability, support for decentralized peer-to-peer sharing, and search by cross-cutting concerns rather than organization by hierarchy. 

Rather than concentrating on the unique value proposition, I added features that competitors had, which were ultimately superfluous, and, in so doing, squandered my competitive advantage while working twice as hard as necessary. I frequently see Product Owners struggle with this. It takes a certain boldness to believe enough in your product vision that you can step away and say "No, I won't do that.". 


# Lessons Learned
## Names Matter
We already covered this in detail. 

## Understanding Competitive Advantage and Being Bold

## Respect for Roles
I learned to respect all of the roles in the value chain
* Sales and Marketing are two different very distinct disciplines and both are **really** hard.
* Gathering requirements is **really** hard.
* Good UX design is **insanely** hard. Design sprints, rapid prototyping, customer feedback, and strong designers are necessary to create good user experiences.
* Good support requires a special kind of person that can be both empathetic to the suffering of others while impervious to the insults of others. That is... you guessed it... **really** hard.

## Users Matter
Agile understands the significance of Users but in 2005 this was something of a revelation: As with writing, audience identification is **everything**. If you do not know your user group you will fail. 

Further, I learned that users deserve respect even when they are trolling you. Supporting the product I received a lot of very colorful and impressively mean messages. After the stinging and burning sensations subsided I usually found actionable insight in most of the e-mails (...most).

