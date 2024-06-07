---
layout: post
author: KWG
date: 2023-09-02
title: KWG's WM2K Guide - Moveset Hacking For Dummies
slug: guide-moveset-hacking-for-dummies
description:
category: wm2k
category-title: WWF Wrestlemania 2000
tags: ["wm2k","guide"]
source: Old Skool Reunion
source-url: http://oldskoolreunion.com/forum/threads/wm2k-moveset-hacking-for-dummies.42018/
assetid: 3ab2050f
ogp:
published: true
---

### Part 1

##### Step 1

Download Project 64 4.0.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_01.png){:.centered-img}

##### Step 2

Create a CAW with the moveset, parameters and even the AI you want [(use the Edit AI code)](https://aki.guide/wm2k/gameshark-ai-menu/).

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_02.jpg){:.centered-img}

##### Step 3

Start a match where your CAW(s) are involved and pause it.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_03.jpg){:.centered-img}

##### Step 4

Go to Debugger -> Memory -> View.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_04.png){:.centered-img}

##### Step 5

Let's dump the moveset! Right click -> Dump, For Player 1's moveset, put "8008DC34" as the start address, "8008DCE8" as end address, filename can be whatever you want it to be, but it has to end in ".bin" and the format has to be "RAW - Big endian (n64)", no more, no less, press dump.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_05.png){:.centered-img}

##### Step 6

Let's dump the parameters/fighting style/artificial intelligence! Same thing as above, just use the following adresses for P1: "8008DCFC" as the Start address, and "8008DD1A" as the end address

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_06.png){:.centered-img}

Done. You should now have the moveset and parameters files.

**Player's Moveset Address:**

    P1 - 8008DC34 - 8008DCE8
    P2 - 8008DD28 - 8008DDDC
    P3 - 8008DE1C - 8008DED0
    P4 - 8008DF10 - 8008DFC4

**Player's Parameters Address:**

    P1 - 8008DCFC - 8008DD1A
    P2 - 8008DDF0 - 8008DE0E
    P3 - 8008DEE4 - 8008DF02
    P4 - 8008DFD8 - 8008DFF6

*Tip: You can dump up to 4 movesets/parameters using Tag Team/Battle Royal matches!*


### Part 2 - REPLACING THE MOVESET

##### Step 1

For this I will use VPW Studio. Make a copy of your rom, to use as the base rom, and create a project using VPW Studio.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_07.png){:.centered-img}

##### Step 2

Go to Project -> File Table.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_08.png){:.centered-img}

##### Step 3

Go to Navigation -> Search (or Ctrl + F) and search for "Wrestler Moveset" or "Wrestler Params" and find the wrestler you want to modify.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_09.png){:.centered-img}

##### Step 4

Right click his moveset or parameter file -> Edit Information (or Ctrl + I).

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_10.png){:.centered-img}

##### Step 5

Choose the path to your file in "Replacement Path".

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_11.png){:.centered-img}

##### Step 6

Press OK, do this to as many files as you need to replace, then press Ctrl + S to save your project, and then choose Build ROM. You're done.

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_12.png){:.centered-img}

### CREDITS

freem - for VPW Studio.

Flashman - for teaching me how to dump.

Keep in mind this modifies the AI too, so you should edit the CAWs AI before doing this.

Have fun.