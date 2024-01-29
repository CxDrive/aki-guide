---
layout: post
author: freem
date: 2021-11-21
title: ROM Addresses - Unlock All
slug: rom-addresses-unlock-all
description:
category: nomercy
category-title: WWF No Mercy
tags: ["nomercy","addresses","rom"]
source: Virtual Pro Wrestling 2 Dojo
source-url: https://www.tapatalk.com/groups/vpw2dojo/unlock-all-code-t290.html#p1296
assetid: ba038833
published: true
---


> Instructions for hacking this onto a ROM:
>
> First, check which region and version of the game you are hacking. This is important, since the locations change based on region and revision.
>
> "z64 ROM address" represents the location to edit in a Z64 format ROM.
> "runtime address" represents where the code is located during execution (a.k.a. memory editor address).
>
> The old/new instructions are given in the general form:
> assembly ; bytes
> where "assembly" is the code represented by the four bytes on the other side of the ";".
>
> Find the four bytes from the "old instruction" and replace them with the bytes from the "new instruction".
>
> NTSC-U and PAL v1.0
> z64 ROM address 0x574E4
> runtime address 800DAFC4
>
> old instruction
> lbu $v0, 0xEE40($at) ; 90 22 EE 40
>
> new instruction
> addiu $v0, $r0, 0x00FF ; 24 02 00 FF
>
> NTSC-U v1.1
> z64 ROM address 0x57444
> runtime address 800D9A94
>
> old instruction
> lbu $v0, 0xD910($at) ; 90 22 D9 10
>
> new instruction
> addiu $v0, $r0, 0x00FF ; 24 02 00 FF
>
> PAL v1.1
> z64 ROM address 0x57344
> runtime address 800D9994
>
> old instruction
> lbu $v0, 0xD810($at) ; 90 22 D8 10
>
> new instruction
> addiu $v0, $r0, 0x00FF ; 24 02 00 FF
>
> -- <cite>freem</cite>
