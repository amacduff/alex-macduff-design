---
layout: post
title:  "Accessibility"
date:   2015-09-17 12:54:56
permalink: accessibility/
categories: the-iron-yard
excerpt: Making your site accessible can be burdensome. But then, so can trying to use a website on a screen reader.
---

## A Daunting Task
This week in my classes at The Iron Yard we've been talking about web accessibility. It has been really eye opening for me. I guess because in the past I have tried to use good contrast and make text large enough in my designs, I thought I was making accessible sites. But as we've been going through this stuff, I've realized how badly I have been missing the mark.

At first, I felt really convicted about my previous lack of attention to this stuff, and I felt excited to learn more about this topic. As we really started delving into this stuff, though, I'll admit my excitement started to wane. There's just so many things to take into consideration, it all felt overwhelming. In a very selfish line of thinking, it seemed like a lot of extra work (and code) for something with no measurable product.

Now, don't get me wrong; I care about accessibility. The trouble for me is just knowing how much to do, and where to start. So I've made a list of ten things to implement in my next project, to strive towards making interfaces that are easy for *anyone* to use.

![Accessibility]({{ post.url | prepend: site.baseurl }}/img/blog/accessibility.png)


## 10 Tips for Designing More Accessible Websites

### Separate content from presentation
Plain and simple: keep your CSS outta your HTML.

### Write clearly and simply
This one is challenging. Basically: organize your thoughts, get to the point, don't talk down to your audience, avoid jargon, use correct grammar, and check your spelling.

### Use proper semantic structure to organize content
Use HTML elements properly. Headings are for structuring content, not styling it. Don't skip a heading because it's not the right size. That's what CSS is for. Don't use lists or tables for layout; that's just silly.

### Use good color contrast
This is another tricky one. Use a tool like [WebAIM's Color Contrast Checker](http://webaim.org/resources/contrastchecker) to check your color contrast.

### Include alt text for images
Use alternative text to describe the content and function of images. Be descriptive, be succinct, and be aware of context. Oh, and be sensible. Don't use alt text for purely decorative images.

### Give links descriptive names
Avoid <em>click here</em> links.

### Provide an option to skip to main content
Truth be told, <em>skip navigation</em> links are a bit burdensome. But then, so is waiting for a screen reader to go through twenty navigation options to get to some real content.

### Design forms for ease of use
Name form fields appropriately and make them tab-able (tabbable?). Also, don't use CAPTCHAs; they're annoying anyway.

### Ensure all content can be accessed with the keyboard alone
This one's not too hard, just put the mouse aside and do a keyboard test. And for the love of Pete, don't hide focus indicators.

### Use ARIA
ARIA (Accessible Rich Internet Applications) is a way to add specificity to your HTML elements. Use roles like <em>navigation</em> and <em>menu</em>, landmarks like <em>banner</em> and <em>main content</em>, alerts like <em>live</em> and <em>atomic</em>, and descriptive form text like <em>described by</em> or <em>labeled by</em>.


## In Summary

Making a website accessible can seem like a truly daunting task. Just thinking about all this stuff makes my head swim a little, and this is a relatively short list. So if I find myself feeling like the addition of these things to my workflow is an inconvenience, I'm going to put my mouse away, close my eyes, and try to use the keyboard and a screen reader to surf the web for a few minutes. I'm pretty sure I'll feel differently afterward.