---
layout: post
title: "DIY RIMS tube, and brewery update"
date: 2014-08-29 08:38:21 -0400
comments: true
categories:
- homebrewing
---

Over the past few days, a bunch of new toys have steadily been arriving at my doorstep. But first, did I mention that [my last post about the brewery](/blog/2014/07/24/downsizing-sucks) can go suck it? <!-- more -->Yeah, I wrote that post late at night while I was feeling a little overwhelmed and like my brewery would never happen. But I woke up the next morning with a renewed sense of purpose and just a generally uplifted can-do attitude. With the support of my amazing wife, I'm going to make this brewery happen. The size of my pots, in the grand scheme of things, doesn't really change how the brewery would be built anyway. Sure, I'll still have to worry about where to put all my beer, but I'll deal with that when the time comes. Every other piece of the brewery would need to be built the same if the pots were 10G anyway, so I'm sticking with the 20G setup.

### Brewery Update

So the brewery build is back on track. Since the last post, I ripped up the bamboo laminate flooring and molding in the basement brew room, and rented and used a concrete floor sander from Home Depot to remove the existing paint on the floor. This weekend is Labor Day weekend and I have a lot of work to do. I need to finish cleaning up around the edges where the concrete sanding left behind a bunch of muck. After that I'll be putting down a coat of garage floor epoxy that I got custom mixed at Lowe's to match the color scheme I want for the brewery.

I'm going for a super sleek/modern industrial look not unlike the [awesome basement brewery](http://www.theelectricbrewery.com/gallery) designed by Kal, the creator of The Electric Brewery (the instructions I used to build my control panel). I'm also pulling on a lot of inspiration from [all the other](http://www.theelectricbrewery.com/testimonials) Electric Brewery setups out there. Even the names of the Valspar paint color swatches are pretty badass: "High Speed Steel" and "Polished Silver". These colors are going to really make all the stainless steel equipment "pop". Those toys I mentioned earlier included diamond plating outlet and switch covers, as well as some really nice looking brushed aluminum sheeting that is going to make a kickass backsplash on the wall behind the kettles. More on all that next week so stay tuned.

### Portable Brewery

The basement brewery project is a huge undertaking and I really won't be able to use it until everything is done and in place. At this point, that's looking like it could still be a few months out. In the meantime, I've been actively researching many other areas of homebrewing. I'm playing around with a lot of stuff around automation with Raspberry Pi and Arduino. I also recently learned about PLCs (Programmable Logic Controllers) which is really interesting to me and I'm sure you'll be seeing a post about all that soon. Anyway, back on track.

One of my goals that is running parrallel to my goal of the basement brewery is the idea of also having a very portable electric brewery that I could potentially take with me and brew at a friends house or at a local brew day. Obviously the 3 kettle 20G HERMS system isn't going to be leaving my basement without something short of a U-Haul. The goals of the portable brewery are:

1. Uses 120v electricity to brew a 5G batch (5G in the keg)
2. Completely modular- can be used in more than one way
3. Supports 2 pumps with standard outlets (separate on/off switches)
4. Uses a single temp probe and PID for auto-tuning precise tempurature setpoints
5. Small footprint, portable
6. Keep it simple, stupid!

So there are several pieces to this setup; the control panel (the brain!) and the separate modules. Right now the pico panel is in a non-working state... I have some debugging to do to diagnose what is going on with the solid-state relay which appears to not be working. For point #2, an example of another way to use this would be a sous-vide in the kitchen (this adds to the importance of a small footprint for the panel), which would involve a smaller heating element plugged into the panel, and a very tiny recirculation pump. Modular brewing options would be the RIMS tube or a brew-in-a-bag (BIAB) pot. Another whacky use would even be to apply this to the cold side of brewing. The PID is just as capable of turning a fermentation chamber on and off according to the low set point as it is for turning a heating element on for mashing/boiling! How cool is that?! Another modular piece of the equation is that the support for "pumps" is really just a couple of auxiliary outlets with switches, so you could plug a fan in there if that applies to the task at hand, or whatever you need. I'm currently thinking through how to make one of the auxiliary outlets have 3 modes: on, off, and auto. The "auto" setting would fire along with the heating element, but still let you switch it off if needed. We'll see though, because it has to align with goal #6!

Here is the Pico Panel build and it being used as a sous-vide controller:

<iframe class="imgur-album" width="100%" height="550" frameborder="0" src="//imgur.com/a/BE1XY/embed"></iframe>

### DIY RIMS Tube

RIMS is a type of electric brewing system whereby the wort is heated directly during the mash as it is pumped over a heating element. This eliminates the need for a dedicated hot liquor tank, making it more portable and cheaper than a HERMS. In HERMS, you typically have 3 vessels, a mash tun with no heat applied directly, a hot liquor tank with heating element and a coil which the wort is pumped (circulated) through without contacting the hot water directly (the water is kept at mash temp by the element), and a boil kettle with heating element.

I found [an old thread on the HomeBrewTalk forums](http://www.homebrewtalk.com/f51/rims-dummies-114997) for a cool design made out of regular stainless steel pipe fittings and opted to go that route rather than buying a pre-made shiny RIMS tube. I like the idea of being able to customize it however I want by unscrewing a fitting or two and maybe adding something in-line or making a change. The fittings are all 1.5" NPT 304 stainless. This thing is super beefy and I'm a little worried that will make it difficult to heat on 120v, but we'll see. I sprung for a tri-clover to 1.5" NPT fitting so I could use a tri-clover heating element enclosure for easy cleaning. I really need to be able to easily dry the element after a brew because they are known to rust if left damp. The heating element I already had from the souse-vide doesn't want to fit nicely inside the RIMS tube, so I'll need to order another one, which is tricky because the product listings on Amazon for these things are notorious for being inaccurate. I really need an Ultra-Low Watt Density element to prevent scorching and to reduce the likelihood of an accidental dry-fire explosions (turning on the element without liquid on it to dissipate the heat) which are guaranteed on the high watt density elements.

<iframe class="imgur-album" width="100%" height="550" frameborder="0" src="//imgur.com/a/5mPuB/embed"></iframe>

Well this blog post took way too long to finish (I started on 8-29 and minimized it until today, 9-5) so I'm going to end it here, but stay tuned for more updates.