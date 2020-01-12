---
title: "Media Purveyor: Lessons Learned "
published: true
---

# Overview
Media Purveyor is a media editing and management application published by Mind Lens Corporation between 2006 and 2007 (I am the only person ever employed by Mind Lens). The application runs on Windows (including Windows 10).
* [Download Media Purveyor v2.9 Installer](/assets/MediaPurveyorSetup29.exe) **NOTE** The uninstaller does work.
* Later versions can be found on the web (v3.2 or maybe even 3.4) but have restricted features unless unlocked through the purchace of a key. The key generator is lost so the most feature rich Freeware version is v2.9.

## Standard Features
* Image Editor with 43 effects, _layers_, varying selection techniques.
* Image analysis (histogram by channel)
* Browser with multi-threaded thumbnail loading (CPU decoding one file while waiting on the I/O for another).
* Feature rich slideshow
* Tons of batch processing features: contact sheets, batch re-name with different strategies, image conversion, scaling/sizing, etc..
* On-line gallery publishing which creates a searchable on-line gallery as an AJAX application (cutting edge for 2006).
* Plugin based architecture for image editing effects, media decoders, encoders, metadata readers, etc..
* Completely custom widget set built for this application with layout managers, custom styling, visual effects.
* File (en/de)cryption and filename obfuscation (creepy feature added because a co-worker suggested it)

![Color Balance](/assets/ColorBalance.jpg){:style="max-width: 100%"}

## Unique Value Proposition
Media Purveyor has a special trick: it can read/write metadata from/to many different types of files without otherwise impacting the file contents. The software uses metadata, branded "Self-Describing Media", extensively to provide
* Portable Lossless Image Editing. The application can store multiple "views" of an image inside the source image file without having to re-encode (which for many formats causes a degradation in quality with each save). 
  * For example, you might take one very nice photo and create a view that crops the image one way and applies a blur. 
  * Another view may crop a different region and apply a sepia filter or an oil painting effect.
  * That one file would contain the original plus two additional views and, since the views are stored inside the file as a lightweight set of commands, the views are portable from one device to the next and add very little to the file size.
* Portable keyword tagging and search. Keywords can be added to images and videos to support cross-cutting concern based searching. Rather than organizing media into artificial taxonomies / hierarchies, a media managers (marketing for example) can search an enormous catalog of media based on the Venn intersection of needs. 
* Portable Schema-Less Data Entry. In addition to keywords, media can be described using user defined "Entry Screens" which are sets of fields (text, list, date, etc.). Each media file described with an Entry Screen contains enough of the Entry Screen schema to enable another client to also edit and search using that Entry Screen. The software has an Entry Screen identity and structural conflict resolution strategy.

# History and Lessons Learned
A few days ago I encountered the v2.9 installer while transfering files off an old computer. I decided to give it a try on my Windows 10 machine and was shocked to find the application worked. Well mostly worked (one dialog popped down under a window rather than popping over requring Alt-Tab to find it; also it throws an error on shutdown). Finding the application led me to reflect on what I had learned from the experience.

## Names Matter
I spent my spare hours developing the application from some forgotten month in 2004 to March of 2006. I was so convinced the "innovative" support for decentralized search would equate to financial success that I finally left a salaried development position to work full-time developing the product. My hopes were high. I thought it would become a household name.

The first problem encountered on the road to making the product a household name was the name itself: **Media Purveyor**

Yikes! As a name "Media Purveyor" _fails_ to be unique, exciting, or informative but _excels_ at conveying an odd combination of 
boring, pompous, and vaguely creepy. I wish I could remember what I was thinking but I doubt I was thinking anything at all (an absence of any thinking is probably the most pervasive thinking error). I was an "engineer" and thought the name unimportant. Didn't the The Bard have Juliet say "That which we call a rose By any other name would smell as sweet"? Perhaps. Even still, no one will buy roses labelled "Squelchy Stink Blooms". 

## Design is Hard
When running the application now, I am stuck by how much is comically and avoidably wrong with the user experience. We'll start with the hyper-animated title screen: You cannot tell from the static image but trust me when I tell you the water is... um... undulating is probably the word. Inside the transparent sphere you will spot small red, green, and blue spheres. These three orbs both spin and move in and out like a nauseating carnival amusement. Why are they doing that? I don't know. I do know you have excellent stomach constitution if you can stare at this screen for longer than 45 seconds without losing your last meal. 

![Title Screen](/assets/MediaPurveyorTitleScreen.jpg){:style="max-width: 100%"}

We move on to considering the main media browser screen. The image is scaled so it might be hard to tell but there are between 11 and 14 bazillion indicators, widgets, doodads, and things to press, click, slide, and twist. Almost every single surface can be right-clicked to reveal a dizzying array of additional options. Hovering over almost anything brings up a tooltip which is closer to a tool-novella. It is a kitchen sink interface with no sense of priority, proportion, weight, balance or flow. 

![Media Browser](/assets/MediaPurveyorBrowserScaled.jpg){:style="max-width: 100%"}

Media Purveyor taught me that design is both important and difficult to get right; often requiring design sprints, rapid prototyping, frequent customer feedback, and the guidance of skilled designers.

## Users Matter
When I first started developing Media Purveyor I didn't really have a customer profile. Obviously one needs to understand users to develop a good user experience (see above). However, it goes beyond that. A vague or absent customer profile impairs marketing, feature priority, pricing, documentation, design, development, and support. As with writing, audience identification is **everything**. If you do not know and build for your user group you will fail. 

For example, when running an ad words campaign you select a demographic indirectly by the words you choose. You pay every time someone clicks on one of your ads based upon the word so you lose money when your ad words attract people unlikely to pay for your product. If you do not target customers with precision it is possible to sell a ton of product and yet have ad expenses many times greater than revenue! A few poorly executed marketing months could eat through all of your capital. 

## Making Money is Hard
I lost money while working 80 hours a week, never really sleeping, and entirely consumed by my product. 

This taught me enormous respect for business plans and those who execute them.

## Product Ownership: Understanding Competitive Advantage and Boldness
The core value proposiitons of Media Purveyor are portability, support for decentralized peer-to-peer sharing, and search by cross-cutting concerns (rather than organization by hierarchy). 

Unfortunately, I spent _most_ of my time and energy adding features which competitors had (feature envy) rather than tuning those that I had which they did not. In so doing, I squandered my competitive advantage by burying the unique value underneath a mountain of superfluous features that were probably better implemented by my competitors. I frequently see Product Owners struggle with this. It takes a certain boldness to believe enough in your product vision to have the courage to say "No, I won't do that.". My personal lack of conviction
* diluted the marketing message
* severely delayed time to market
* ruined the user interface 
* increased ongoing engineering and support costs (code is a liability; everything you build must be supported)

## Respect for Support
In supporting the product I learned that good support / customer care requires a special kind of person that can be both _empathetic_ to the suffering of users and  _impervious_ to user insults all while _actively listen_ for the informational content. I received a lot of very colorful and **impressively** mean messages. I found actionable insight in most of those cruel e-mails (...most). 

## Synergy
When I first began developing the product I would typically _start_ with the UX or Technical design of a feature I thought would be "awesome". I considered only the engineering costs. 

This was a disastrous strategy. 

By the end, I learned to integrate most, if not all, facets of the value chain 
* can I sell this? for how much?
* can I market this? can I grab someone's attention in a few words? explain this feature to a stranger in less than twenty words?
* is this changing the inertial center of the application? is this consistent with the goal?
* can I write the documentation for this?
* does this change deployment? can we upgrade? 
* can I support this when it breaks? can I easily explain failure cases, remedies and mitigation to end users?
* how does _adding_ this feature _change_ the user perception of existing features?

## Too Late
I learned many valuable lessons but I learned them far too late. Eventually I ran out of my own money (never solicited VC; yet another mistake) and returned to collecting a paycheck solving problems for other people who had done the hard work of finding paying customers and inventing good names. 

