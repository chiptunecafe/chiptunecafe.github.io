---
author: Quirby64
comments: true
date: 2019-02-23 14:22:53+00:00
excerpt: <p style="white-space:pre-wrap;"> During the Microcomputer Craze of the late
  70’s and early 80’s, the computer market saw a massive upsurge in the amount of
  new computers hitting the scene. Many famous sound chips widely used in the chip
  scene first debuted in computers that were released during this era, with probably
  the most well known example being the SID Chip in the Commodore 64. However, not
  all sound chips from this era were as popular as the aforementioned SID…</p>
layout: post
slug: 2019-2-19-the-comx-35-viscdp1869-a-strange-chip-for-an-old-machine
title: 'The COMX-35 VIS/CDP1869: A Strange Chip for An Old Machine'
wordpress_id: 20
categories:
 - blog
tags:
 - Tech
---

During the Microcomputer Craze of the late 70’s and early 80’s, the computer market saw a massive upsurge in the amount of new computers hitting the scene. Many famous sound chips widely used in the chip scene first debuted in computers that were released during this era, with probably the most well known example being the SID Chip in the Commodore 64. However, not all sound chips from this era were as popular as the aforementioned SID. Many of these ancient sound chips have faded into relative obscurity, rarely ever seen mentioned on the modern chip scene.

One of those forgotten chips is the Video Interface System, or VIS for short. The VIS was the chip present in the COMX-35, a home computer released in 1983. The chip was made up of two sub-chips, one, the CDP1870, for video and the other, the CDP1869, for audio. As if it wasn’t obvious, we’ll be focusing on the latter in this article. The CDP1869 has two channels available: one, a square wave tone with an impressive range of 8 octaves, and the other a white noise generator that has 8 accessible pitches. With these, they had volume control over 16 steps.

Two ways of inputting notes exist, the simpler MUSIC command and the more complex TONE command. MUSIC inputs the notes in the solfege system, the classic Do Re Mi method you learned in elementary music class. TONE, however, had a bit more math involved. Taking one of many several very high “input frequencies”, you would divide this number but anything from 1 to 128, and the resulting number is the frequency. For example, if we take the first input frequency, 5537.1094Hz, by, say, 46, we get the end number of roughly 120.3719Hz, or just about the note B2. Neat, huh?

But there’s always more to be done when it comes to bringing a chip to its limits. As technology got more advanced, bringing sounds in from the real world became more and more of a mainstream practice. The holy grail of this practice, the sampler, was quickly gaining traction, and older chips, including the VIS, needed to follow suit. This was done with PCM, or Pulse-Code Modulation, a process used in everything from old sound chips  modern day CDs. From here is the start of a reiteration of Café OG Pegmode’s explanation of PCM, as he actually knows what he’s talking about. Most of it has been unchanged, as he did a great job turning such a complex concept into a well-written explanation. 

As we’re told in science class, sound is basically matter that is undergoing some kind of physical compression - air particles, rope, speakers, you name it. Obviously, we can represent this as a waveform, where how much compression at specific time intervals is measured in the vertical axis, or amplitude. This reading can be put over time. Say, for example, we have a sine wave (1). Sampling, here, would be re-creating this wave through a series of pops or pulses. (2) If you make the height of the rectangle the same as the amplitude of the sine wave, you'll notice that your rectangles make an approximation of that sine wave. (3)

You'll notice that the "thinner", or the shorter the distance between the pops or pulses, the more like the original sine wave it will look like. Because the horizontal section of this wave represents time, the measure of this "thinness" is what we call sample rate, which is how often we are placing a pop or pulse. Now, if you think of a vintage sound chip - the most BASIC type, say, the COMX-35 - You can make some kind of sound with controllable volume, which the C-35 can certainly do. 

So, applying this to what I just described, if you make a pop or pulse, that is approximately that same volume, just as the sine wave looks, you’ll make something that looks like that sine wave. And just the same with the original, the more we copy (sample) the values of the original, the close to that sine wave we’ll get. If you understand this concept, and apply it to any arbitrary sound - me talking, a dog barking, anything - and use that same concept, making something that roughly matches that original, you can start to see how you produce samples.  

There’s another factor as well I haven’t mentioned, which is bit depth. It’s a fairly simple thing to understand if you understand sampling rate. It’s the same kind of concept, but instead of dealing with time or how fast you do something, it’s about how many chunks of volume you can create. For example, if you’ve ever worked with the GB, 2A03, or SID, you’ll know that the square wave channels have 16 possible volume levels, from HEX 0-F. So from that, bit depth just means how many volume levels are possible. Say if we were to plot that sine wave again, and we plot those pops or pulses with it, but, we limit the height (amplitude/volume) of those waves to what is possible on, say, the GB pulse channels. You’ll notice there’s a bunch of areas where the height of the sine wave doesn’t match up with a value that is possible on the GB, so we make an approximation by rounding to the closest value that we can make.

So if you combine everything I just went over, you can program a sound chip to make pops or pulses very quickly at corresponding volumes to what you’re trying to recreate to make it. This is kind of simplified, but it’s my attempt at an overview of how this works, in what I’ve tried to make simple terms. The smaller and smaller the distance between those pops or pulses, the higher the quality of the sound. I’d like to point out that the subject of sampling can get very complicated very quickly - with all the different methods of sample creation, such as Delta sampling used in the 2A03. But for old systems that were never meant to play back samples, this (PCM) is the method that’s most common. And thankfully, it’s the most simple. For further reading, I would highly recommend this article: [ http://sid.kubarth.com/articles/the_c64_digi.txt](http://sid.kubarth.com/articles/the_c64_digi.txt)  

With that wonderful explanation by Pegmode out of the way, I’d like to express that this type of sampling was used in the COMX-35. Examples can be found in different media produced for the computer, such as JunioR’s “Get Your Gadget,” an interesting little shoot ‘em up game where you pilot a helicopter and search for the titular gadgets. The game utilizes PCM sound effects that gives a degree of gritty realism to the sound design. The CDP1869 was certainly not the only chip to be lost to time, but it is representative of how there are hidden gems out there waiting to be discovered. Hopefully this explanation about what goes on with a chip like this, and how programmers were able to get real-life sounds into these little bits of technology, will inspire others to search for those hidden gems too.



![ The COMX-35, styled as the “Clever Computer.” ](https://images.squarespace-cdn.com/content/v1/5bfb3cac1aef1da317d0f89a/1550739060919-S7JK9PNLCMJ7X4C27K4Z/ke17ZwdGBToddI8pDm48kFM8Zu7vOdlqUu5LePeU4mtZw-zPPgdn4jUwVcJE1ZvWEtT5uBSRWt4vQZAgTJucoTqqXjS3CfNDSuuf31e0tVHe97f80xQAlueAiBjb4K3hBl_65ZxbJ4YVBBxVHCvAwqEcAfnVBrEqrgp1UxUHGkY/comx.png?format=original)  The COMX-35, styled as the “Clever Computer.”




![  (1)  ](https://images.squarespace-cdn.com/content/v1/5bfb3cac1aef1da317d0f89a/1550725989391-R42AHORF392BL387VHRD/ke17ZwdGBToddI8pDm48kJIp7GrDRrjUIhADgwlEQj5Zw-zPPgdn4jUwVcJE1ZvWQUxwkmyExglNqGp0IvTJZUJFbgE-7XRK3dMEBRBhUpww_HMZpLcsFC2IdUdkwt4bFhyHNy3LuHQlix92_4FLAQOKKruPUTdxq800wTpAZfc/sine.png?format=original)   (1)  




![  (2)  ](https://images.squarespace-cdn.com/content/v1/5bfb3cac1aef1da317d0f89a/1550726122068-UNUA4VYA7I2FI3YTXFSJ/ke17ZwdGBToddI8pDm48kFyQ3VAzk-SArSjF49stuJ9Zw-zPPgdn4jUwVcJE1ZvWQUxwkmyExglNqGp0IvTJZUJFbgE-7XRK3dMEBRBhUpwXcxh7GlDk5Z98o1HOgz30X-t2rII8J2LNeYsZ-tOZNUv2AeHBuElk6KCdfBGJ7xA/gDCDmiD.png?format=original)   (2)  




![  (3)  ](https://images.squarespace-cdn.com/content/v1/5bfb3cac1aef1da317d0f89a/1550726651314-4Y40B4E9L6Q95NJ8I57V/ke17ZwdGBToddI8pDm48kAsd8-2oiAgHFCHfvmAQtv1Zw-zPPgdn4jUwVcJE1ZvWEtT5uBSRWt4vQZAgTJucoTqqXjS3CfNDSuuf31e0tVHVEwn8vA-ZGbKOiNB7_MIrbkf2JPafbY9oRPw20RSxZqQvevUbj177dmcMs1F0H-0/waveform2.png?format=original)   (3)  




![ A screenshot of “Get Your Gadget.” ](https://images.squarespace-cdn.com/content/v1/5bfb3cac1aef1da317d0f89a/1550739459673-9IE7NSCEGR45O9L789CD/ke17ZwdGBToddI8pDm48kFTEgwhRQcX9r3XtU0e50sUUqsxRUqqbr1mOJYKfIPR7LoDQ9mXPOjoJoqy81S2I8N_N4V1vUb5AoIIIbLZhVYxCRW4BPu10St3TBAUQYVKcW7uEhC96WQdj-SwE5EpM0lAopPba9ZX3O0oeNTVSRxdHAmtcci_6bmVLoSDQq_pb/maxresdefault.jpg?format=original)  A screenshot of “Get Your Gadget.”
