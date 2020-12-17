# :rainbow: I'm probably one of the biggest dumbass

## Contents
- [Who am I](#who-am-i)
- [My profile character](#my-profile-character)
- [Contributions](#contributions)
- [Programming languages](#programming-languages)
- [Software freedom](#software-freedom)

## Who am I
**First of all, I'll be offline for next 1.5 years(probably), due to millitary enlistment.**

I am random Korean person, and I'm interested in making various stuff, including:
### Software
It's been at least 7~8 years since I started learning computer programming. The fact that I can tell computer to do whatever I want is just fascinating, and that's why I kept digging into software development for years and years.

### Music box covers
https://www.youtube.com/channel/UC3HukT1x0zzedDeex_5pt6Q

This is probably one of the most popular things compared to other things I am doing.
I was originally doing something called "Note Block Sound Covers", which are cover songs I created using Minecraft's Note Block sounds.
And at **one point**, I've even wrote some custom software for creating videos for my covers:
- NoteBlockVisuals(or something like that, I don't remember the name correctly): Creates visualized output from `.nbs`(Note Block Studio) or `.xm`(from MilkyTracker) file. Unfortunately I lost the source code because **I formatted wrong drive using ```dd```.** Please double-check the destnation before wiping any drive. Initial version was written in Java inside Processing, later version was written in C#.
- NBSVisuals(https://github.com/YeonJi2/NBSVisuals): A visualizer program written for OpenComputers(a Minecraft mod that adds Lua compatible computers). Used it once, and then **trashed it** because it was too slow and unreliable. OC was just too slow, and I think it was still unreliable even with an OC emulator. Of course I tried to fix it, but I eventually gave up. Written in Lua(of course).

Then I've started creating Music box covers at some point, which was eventually more successful than NBS one. I used the same software for both Music box and Note Block sound covers, so I was able to share most of the source code for both.

But currently I am NOT using any of these after switching my music software to LMMS, because I haven't had any time to add MMP(LLMS's file format) file support. I am planning to write new version that just accepts a audio file and renders waveform to a video, but I would need some free time first.

### Twitch live streaming
**NOTE**: I **ONLY** use Korean in my streams, so please do **NOT** use English. I "can" speak English, but it is very difficult to use two languages at the same time.

https://www.twitch.tv/yeonji2/

This is relativly unsuccessful(yet), but I still enjoy talking with viewers, and playing some games occasionally. I've also wrote some sutff for streaming purposes:
- A simple SDL app that redirects microphone input to HDMI output: I used this when I was running GNU/Linux on both of my computers(main desktop and streaming laptop). This redirected microphone input to HDMI output(which was connected to my capture device). It did work, but using this resulted distorted sound when doing voice chat on Discord. Later I discovered the same issue after setting up the same thing using PulseAudio's built-in capabilities, and I don't know why. This was written in C++ if I remember correctly, and this is also no longer on my system. I probably lost it very long time ago.
- **(Still used)** Server/client for uncompressed camera streaming: The server runs on a Raspberry Pi, and sends raw YUV420 video stream from native camera port(CSI) through TCP socket, **without any compression**. The client side is a SDL application that displays whatever it received from TCP stream(SDL's native YUV support made this super easy). Both side are written in Rust, and I might end up releasing source code for this. This system acts as rudimentary webcam on my live stream, though I don't display live webcam very often. Also, because it is uncompressed transfer on local network, there's absoultely **zero** latency.

Fun fact about last one is that I initially wrote server for the Android using Kotlin, but I ended up going to RPi route because my phone kept overheating. Why it overheated? Probably because I was sending a lot of data over Wi-Fi, but I'm not 100% sure.

Also, I have a unknown issue: some of my GNU/Linux machines keep suddenly losing wired network connection and dropping down from 100Mbps to 10Mbps link. Thankfully reconnecting the cable does fix the issue temporarily, and this does not happen during active data transfers(this doesn't heal already broken 10Mbps connection though). If you have any idea about this issue, please send me DM on my Twitter(@yeonjitw).

Lastly, somehow some people started calling me girl as a joke, and then it became a YeonJiKun meme. Now some people want me to do :dress: cross-dressing. ~~I've (sort of) tried it already, and it was terrible.~~

### Artwork
While I'm not good it at all, I also draw some art. In fact, the profile picture you see on my profile is my drawing. And as you've probably guseed it, I also draw various arts for both my YT channels and Twitch channel.

And there is **one** software I wrote for drawing:
- **(Still used)** Graphics tablet screen selection utility for X11: This is useful tool for setting target screen when using X11 with multiple displays. As you might know, X11 maps the tablet to entire display range, which is usually **NOT** desirable when drawing anything. There are already tutorials about this, but those use xinput utility to manually set CTM(Coordinate Transformation Matrix), which tells X11 how to calculate final position using input position. This does work, but it is really inconvenient. So I created a utility that does all of these, including CTM calculation. But it still has some issues, and I don't have time to fix it unfortunately. This is written in Rust, but the only X11 wrapper I found is unsafe one. So my code contains a lot of unsafe code(I tried to be careful though).

## My profile character
My profile character is male, even though it may look like female because of his long hair. I chose long hair just because that's what I wanted.
He is externally a human, internally a spider. And he is wearing some kind of uniform, with big ribbon below his neck. Also, while it is not shown in the picture, he is wearing dark gray pants.

**Fun fact**: Even when I had short hair, many people thought my character was actually girl. Not excatly sure why...

## Contributions
As mentioned, I **am** probably one of the biggest dumbass.
But **because** I am dumbass, sometimes I use software in incorrect ways and discover bugs caused by bad handling:
- https://github.com/rust-lang/rust/issues/73112: Rust compiler had a bug during `repr(aligned)` related error handling. I didn't even know how to replicate the error with minimal code, but thankfully Rust devs found that it was cross-crate related issue.
- https://github.com/PistonDevelopers/freetype-rs/issues/234: Creates duplicate pointer in some unexpected senarios, which eventually causes segfault.

I don't do code contributions however, because I am not confident enough to do that. Plus, not only I am dumbass, but I am also scared of a lot of things.

## Programming languages
**NOTE** I haven't tested any of code listed below. All of these are written using my memory.
```rust
// DO NOT TRY THIS AT HOME!
match gender {
  Gender::Male => {
    // Nothing to do
  }
  Gender::Female => {
    // This would not viloate Rust's memory safety, but I'm pretty sure it will violate other safety...
    unsafe { yeonjikun.set_gender(Gender::Female) };
  }
  _ => panic!("what do you want to become?!")
}
```
For older public projects, I used C/C++. But I am currently using Rust for most of the time, even though I haven't uploaded any Rust project yet.
(This is mainly because I am trying to avoid uploading new projects unless it becomes "usable" state)

Also, I don't think I'll be developing my own C/C++ apps again, since Rust can cover anything I was doing with C/C++ before.

Some other languages I've tried in the past:
### Emacs Lisp
```elisp
(setq result (mapcar (lambda(x) (* x 10)) '(1 2 3 4 5 6 7 8 9 10)))
```
### Go
```go
plzDontTouchMe <- "idk"
```
### Python
```python
yeonjikun = Person(gender="male")
```
### C#
```cs
public partial class YeonJiKun {
  // Left side of my brain.
}
////////////////////////////////////////
public partial class YeonJiKun {
  // Right side of my brain.
}
```
### Java
```java
public class YeonJiKun extends Person implements Male, Idiot, WhatAmIDoing {
  // ...
}
```

## Software freedom
I've started taking software freedom seriously, and I've now moved most of my stuff from Free(as in freedom) Software. I've even decided to move from Clip Studio Paint Pro(which I've paid for not too long ago) to GIMP. The freedom allows user to modify and distribute(modified or unmodified) the software, so devs ususally don't put things that users do NOT want(ads, telemetry that cannot be disabled, etc...).

So I won't be testing my software on Windows, unless I wanted to test it for some reason. Some stuff might work on Windows, but I won't be providing any Windows instructions for any of my future projects.
