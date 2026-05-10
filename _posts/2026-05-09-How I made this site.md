---
layout: post
title: How I made this site
tags:
  - programming
---
web design is my passion 

A while ago, I was playing around with html on neocities, so I had some html files worked up already. I was also inspired by [this personal site](https://macwright.com/) to use Obsidian and Github Pages + Jekyll (he describes his process [here](https://macwright.com/2023/12/14/blog-about-blog)). Since Obsidian and markdown files are easy to work with, I figured it was worth a try. 

I tried using a pre-built theme, [Hyde](https://hyde.getpoole.com/), and it was working fine at first, but then I noticed that for some reason, the css formatting would completely break for any page dedicated to a single post. I gave myself an aneurysm trying to fix this, but no dice. Finally I just built up a theme from scratch, thanks to the old html files I had written up beforehand. 

Now I can add files to Obsidian, do any writing there, and then use the Obisdian Git community plugin (thank you to [this tutorial](https://forum.obsidian.md/t/the-easiest-way-to-setup-obsidian-git-to-backup-notes/51429) on how to use it) to push the changes to the github repository. I have yet to figure out how to use templates to make new files with the correct titling convention and front matter. 

Some considerations, as a beginner with this kind of thing:
- My original html+css had the sidebar and content specified using absolute measurements, which probably isn't the way to go. (e.g. sidebar is 30px wide, add 30px of padding to the left of content.) I changed this to use a flex container so that the sidebar would naturally sit next to the content. 
- Struggled for a bit with the sticky sidebar: since the sidebar and main content were in a flex container, this made the sidebar have the same height as the main content. [This Stack Overflow post](https://stackoverflow.com/questions/44446671/my-position-sticky-element-isnt-sticky-when-using-flexbox) helped a lot. Turns out you just need to add `align-self: flex-start` to the sidebar to make the height fit its contents, instead of match the other div. 
- The sidebar formatting doesn't work well for mobile, so I had to figure out how to alter the css on mobile browsers. [This Stack Overflow post](https://stackoverflow.com/questions/14942081/detect-if-a-browser-in-a-mobile-device-ios-android-phone-tablet-is-used) was helpful; it gives a somewhat hacky way of detecting mobile browsers: `@media (any-pointer: coarse)`. On mobile, I just switch the `flex-direction` from `row` to `column` (and make the divs fit 100% width). 
- I was never aware of the github web editor until now?? It's so much easier to use when editing files, and all you need to do is hit the `.` key while on a repository :0

