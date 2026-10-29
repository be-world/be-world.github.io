---
layout: post
title: "Y2K photo converter: Bring nostalgia back!"
description: A browser-only photo tool that turns modern pictures into early-2000s camera and phone shots.
date: 2026-10-28
categories: projects
permalink: /:categories/:title
---

I wanted photos that looked like they came from a camera I do not own.

Early digital cameras and phones had a specific kind of bad. Low resolution, heavy compression, weird color, a little noise. It was not film grain. It was a crisp, cheap, slightly broken look, and it still hits the nostalgia nerve for me. I kept taking pictures on a modern phone and wishing I could push them back into that era. Buying an iPhone 3, a Cyber-shot, or a Razr just to get the look felt like the wrong project. Building a small website felt like the right one.

[Y2K Photo Converter](https://y2k-photo-converter.vercel.app) is that site. You drop in a photo, pick a camera or phone from the early 2000s, and optionally lay a filter on top. Then you download or share the result. The source is on [GitHub](https://github.com/be-world/y2k-photo-converter-vercel).

## What it tries to imitate

Each device is its own processor. I did not want one generic "vintage" slider. A Kodak EasyShare and a Sony Cyber-shot did not fail in the same way, so they should not look the same.

The cameras currently in the app:

- **Sony Cyber-shot DSC-W35**, cold, slightly desaturated, with that flash spotlight and dark corners
- **Kodak EasyShare C875**, warm reds and yellows, closer to Kodak color than to a neutral sensor
- **Nikon Coolpix S210**, the indoor orange cast and luminance grain
- **Fujifilm FinePix F20**, smoother and waxier, from aggressive noise reduction
- **Canon IXUS 70**, sharper and cooler

The phones go further down in quality, which is the point:

- **Motorola Razr V3** and **Nokia 6600** at VGA, crushed blacks, muddy JPEG
- **BlackBerry Curve 8520**, soft focus and muted color
- **iPhone 4**, a step up, still not a modern camera
- **Samsung Galaxy S II**, the moment phone cameras started trying to look sharp on purpose

On top of that I added filters in the spirit of the first Instagram ones. Early Rise, Lomo, Cross Process, Golden Hour, and the rest. The camera sets the hardware. The filter is the extra touch people used to slap on before posting.

## Why it stays in the browser

I wanted other people to be able to use it, and I did not want their photos on a server. Every conversion runs on the device, in the browser, with the canvas and a bit of WebGL. The picture is never uploaded. There is no account. You keep the file.

That also kept the project small. Vanilla JavaScript, no backend, hosted as a static site. The heavy part is pixel work: color curves, noise, vignette, and scaling the image down to something a 2006 sensor would have produced. Phone frames are composited on top when you want the picture to sit inside the hardware, not just look like it.

## What I learned shipping it

The look is in the flaws. Resolution, white balance, and compression matter more than a pretty color grade. Once those were specific to a real device, the photos started to feel remembered instead of filtered.

It is live if you want to try a picture you already have. I still do not own the hardware. I do not think I need to.
