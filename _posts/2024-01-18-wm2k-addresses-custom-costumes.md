---
layout: post
author: C-Drive
date: 2024-01-18
title: Memory Addresses for Custom Costumes
slug: addresses-custom-costumes
description:
category: wm2k
category-title: WWF Wrestlemania 2000
tags: ["wm2k","addresses"]
source: C-Drive
source-url:
assetid: 58eafef8
published: true
---

### <a name="String Conversion Tool"></a> String Conversion Tool

Putting the string conversion tool up top for quick access.  Read the [Details](#Details) section below for the explanation.

The tool below accepts a string of bytes separated by a space - depending on where you copy your data from, you may need to reformat it for this tool.  For an example look to the [Details](#Details) section below.

----

<div class="form-floating w-75 mx-auto d-block toolarea">

<textarea class="form-control" style="height: 90px; padding: 1.5rem" id="input"></textarea>
<label for="input">55 Byte Input String:</label>
</div>


<button class="btn btn-primary btn-lg mx-auto d-block" type="button" style="margin: 1rem" onclick="genValue()">Output</button>

<div class="form-floating w-75 mx-auto d-block toolarea">
<textarea class="form-control" style="height: 90px; padding: 1.5rem"  id="output"></textarea>
<label for="output">36 Byte Output String:</label>
</div>




----

### <a name="Details"></a> Details

Load up WM2K into Edit mode and select your newly costumed Edit.

Memory addresses are from **80171768 - 8017179E**, and the string will be 55 bytes.  The below is an example string (feel free to test it in the tool above).


03 02 00 3D 07 0A 31 05 08 04 05 00 17 00 00 0C 00 00 2A 00 00 19 00 00 14 00 00 04 03 0A 04 08 00 05 02 00 11 00 00 03 06 00 0B 03 00 0E 05 00 13 06 1F 13 09 00 02 00


Once you've copied that 55 byte string from memory, you can paste it into the first text area in the [String Conversion Tool](#String Conversion Tool) above.  Hit the **Output** button and it will generate the typical 36 byte costume string used for costume replacement in Wrestlemania 2000.

The table below details what each byte of the string represents:

| Offset      | CostumeDataType |
| ----------- | --------------- |
| Offset 0x00 | Body Size |
| Offset 0x01 | Skin Color |
| *Offset 0x02* | *unused* |
| Offset 0x03 | Ring Attire |
| Offset 0x04 | Ring Attire Color 1 |
| Offset 0x05 | Ring Attire Color 2 |
| Offset 0x06 | Upper Attire |
| Offset 0x07 | Upper Attire Color 1 |
| Offset 0x08 | Upper Attire Color 2 |
| Offset 0x09 | Head Shape |
| Offset 0x0A | Hair Color |
| Offset 0x0B | Unknown 1 |
| Offset 0x0C | Face Number |
| *Offset 0x0D* | *unused* |
| *Offset 0x0E* | *unused* |
| Offset 0x0F | Hair 1 |
| *Offset 0x10* | *unused* |
| *Offset 0x11* | *unused* |
| Offset 0x12 | Hair 2 |
| *Offset 0x13* | *unused* |
| *Offset 0x14* | *unused* |
| Offset 0x15 | Facial Hair |
| *Offset 0x16* | *unused* |
| *Offset 0x17* | *unused* |
| Offset 0x18 | Masks, Etc |
| *Offset 0x19* | *unused* |
| *Offset 0x1A* | *unused* |
| Offset 0x1B | Gloves |
| Offset 0x1C | Gloves Color 1 |
| Offset 0x1D | Gloves Color 2 |
| Offset 0x1E | Left Elbow Pad |
| Offset 0x1F | Left Elbow Pad Color |
| *Offset 0x20* | *unused* |
| Offset 0x21 | Right Elbow Pad |
| Offset 0x22 | Right Elbow Pad Color |
| *Offset 0x23* | *unused* |
| Offset 0x24 | Tattoo |
| Offset 0x25 | Unknown 2 |
| *Offset 0x26* | *unused* |
| Offset 0x27 | Wristband |
| Offset 0x28 | Wristband Color |
| *Offset 0x29* | *unused* |
| Offset 0x2A | Left Knee Pad |
| Offset 0x2B | Left Knee Pad Color |
| *Offset 0x2C* | *unused* |
| Offset 0x2D | Right Knee Pad |
| Offset 0x2E | Right Knee Pad Color |
| *Offset 0x2F* | *unused* |
| Offset 0x30 | Boots |
| Offset 0x31 | Boots Color 1 |
| Offset 0x32 | Boots Color 2 |
| Offset 0x33 | Entrance Attire |
| *Offset 0x34* | *unused (likely Entrance Attire color)* |
| *Offset 0x35* | *unused* |
| Offset 0x36 | Entrance Weapon |

<script>
		function genValue() {
			var input = document.getElementById("input").value;
			const iArray = input.split(" ");
			document.getElementById("output").value = iArray[9] + " " + iArray[10] + " " + iArray[11] + " " + iArray[12] + " " + iArray[15] + " " + iArray[18] + " " + iArray[21] + " " + iArray[24] + " " + iArray[0] + " " + iArray[1] + " " + iArray[3] + " " + iArray[4] + " " + iArray[5] + " " + iArray[6] + " " + iArray[7] + " " + iArray[8] + " " + iArray[27] + " " + iArray[28] + " " + iArray[29] + " " + iArray[36] + " " + iArray[37] + " " + iArray[39] + " " + iArray[40] + " " + iArray[30] + " " + iArray[31] + " " + iArray[33] + " " + iArray[34] + " " + iArray[42] + " " + iArray[43] + " " + iArray[45] + " " + iArray[46] + " " + iArray[48] + " " + iArray[49] + " " + iArray[50] + " " + iArray[51] + " " + iArray[54];
		}
</script>
