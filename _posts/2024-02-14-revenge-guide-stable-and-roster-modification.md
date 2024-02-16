---
layout: post
author: ragdas
date: 2024-02-14
title: Module 1 - Stable & Roster Modification
slug: stable-and-roster-modification
description:
category: revenge
category-title: WCW-nWo Revenge
tags: ["revenge","guide"]
source: Virtual Pro-Wrestling 2 freem Edition Discord
source-url:
assetid: 899107ef
ogp:
published: false
---

### Lesson 1

I'm gonna share some spreadsheets
similar to the ones I built for myself in making Salvo
anyway
before we begin
I'm going to assume everyone has done the part where they have a separate ROM
that they're using as the base ROM for their Revenge project file

in your scratch ROM, please make sure your equivalent part of the ROM looks like mine

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_01.webp){:.centered-img}

at 667DC, type in 2404FFFF, and at 667F0, also type in 2404FFFF
this will unlock all characters from the get-go
and will make the rest of this easier, e.g. when costume hacking
here's where we'll get started
Attachment file type: spreadsheet

[WCW-nWo Revenge - Roster Editing Exercise.xlsx](../../assets/files/{{ page.assetid }}/{{ page.assetid }}_WCW-nWo_Revenge_-_Roster_Editing_Exercise.xlsx)

13.52 KB
Attachment file type: spreadsheet

[WCW-nWo Revenge - Wrestler Overview Data.xlsx](../../assets/files/{{ page.assetid }}/{{ page.assetid }}_WCW-nWo_Revenge_-_Wrestler_Overview_Data.xlsx)

120.47 KB
there are two sheets here:
1) Roster Editing Exercise
2) Wrestler Overview Data
The overview data is where I'd start, but I can understand that some of you might be more interested in moving people from one place to another
so I'll quickly touch on an exercise
regarding making changes to stables
let's take a look at this

![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_02.webp){:.centered-img}

this part of it tells you what the address of the first wrestler in that stable is
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_03.webp){:.centered-img}
given that this is the first stable in the game, my advice is to not change this
it is more likely that you'll change every stable downstream of this one
When you do have to change this, please remember that every wrestler is worth 4 bytes
so, if you wish for the stable to start with the wrestler prior to the one it's starting with now
you subtract 4 (in hex) from whatever the current address is
if you wish for it to start with the wrestler after the one it's starting with now
you add 4 (in hex) to the current address
so, if I wanted the stable to start with the Giant, and effectively dummy out Hogan in the process, I would change 8003A1EC to 8003A1F0
anyway
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_04.webp){:.centered-img}
this part of it is the wrestler counter
it only goes up to 9, anything after, the game ignores
so you can't just stack stack stackaroo
in the future, someone may be able to make VPW64 style wrestler select screens that make this a moot point
but for your sake, please keep the limit in mind
If you want to dummy out Curt Hennig, all you'd have to do is change this value from 0009 to 0008
now where it can get interesting is, "what if I want to move Curt Hennig to the Wolfpac?"
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_05.webp){:.centered-img}
1) Keep nWo White's 8003A1EC the same
2) Change nWo White's 0009 to 0008
3) Subtract 4 from nWo Red's 8003A210 to get 8003A20C
4) Change nWo Red's 0005 to 0006
this is where this information is located in ROM
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_06.webp){:.centered-img}
You can see the first set of values = nWo White (the 00BE is their stable header texture; you can ignore this)
so if you've done the changes to your scratch ROM to unlock everyone
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_07.webp){:.centered-img}
this is what you should see
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_08.webp){:.centered-img}
it'll be pretty embarrassing if I goof here eh
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_09.webp){:.centered-img}
but yes, note the changes in red
et voila
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_10.webp){:.centered-img}
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_11.webp){:.centered-img}

### Lesson 2

Aite people
time for the next exercise
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_12.webp){:.centered-img}
we're going to be looking at this column today
I've arranged this for you so that it's easy for you to know where everyone is in the original game
I'm going to do an 'easy' version of this exercise with you
and then promptly show you what a step beyond this looks like
With that said, here's the 'easy' version of the exercise
We're going to do a very simple adjustment to the sequence of the roster by switching Hulk Hogan with The Giant
I will assume you're using HxD for this
1) Take Hogan's value (80 03 93 90) and copy it
2) Go to HxD and press Ctrl+F to open up the "Find" dialog box
3) Paste Hogan's Wrestler Address that you just copied into the "Hex values" tab
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_13.webp){:.centered-img}
out of habit, I tend to press "Search All", because it tells you the offset at the bottom
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_14.webp){:.centered-img}
4) You can see that the blue portion of this screenshot is Hogan's wrestler address; the portion I highlighted in yellow is Woman's (80 03 A1 2C), which is at the bottom of your spreadsheet
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_15.webp){:.centered-img}
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_16.webp){:.centered-img}
5) All we're going to do now is switch the Giant with Hogan; to do this, take Giant's Wrestler Address (80 03 8E BC) and paste it over Hogan's Wrestler Address, and then likewise take Hogan's Wrestler Address (80 03 93 90) and paste it over Giant's
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_17.webp){:.centered-img}
6) Save your changes in HxD and then rebuild your rom in VPW Studio (Ctrl+Shift+B)
this is what you should end up with
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_18.webp){:.centered-img}
That's the first part of the lesson done; directly reply to this message if anything in this portion of the lesson is confusing you
If you were successfully able to do that, I will now teach you something a bit more advanced
you don't have to follow this exercise to the letter, this is meant to teach you part of my workflow

at this point, you'll see that our stables look like this right now:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_19.webp){:.centered-img}
I tend to use the Excel to keep track of these kinds of changes
but once you get comfortable enough, you should be be fine just searching the nWo White address (8003A1EC) and making direct changes to that section

### Lesson 3

anyway
what we're going to do is switch nWo Red entirely with nWo White
The way i start this sort of exercise is by first excising the slots I intend to move; in this case it's a whole stable, so it'd look something like this
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_20.webp){:.centered-img}
Then I adjust everything so that the gaps are closed:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_21.webp){:.centered-img}
there's a gap just big enough for all the nWo Red people
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_22.webp){:.centered-img}
so now in your Excel file, you should see that there are no more gaps
to do a quick audit, click on Kevin Nash's name and highlight every name until Woman's: the number of values you should get is 90
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_23.webp){:.centered-img}
now, what you'll do from here is go to HxD and repeat the step where you search for Hogan's wrestler address

Remember, it'll take you here:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_24.webp){:.centered-img}
After you've arrived at this specific offset
make sure you're at this starting point
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_25.webp){:.centered-img}
Then press ctrl+E to open the "Select Block option"
your list of wrestler addresses has a length (in hex) of 168
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_26.webp){:.centered-img}
you should now have the whole thing selected:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_27.webp){:.centered-img}
go back to your spreadsheet and select all the values in the wrestler address column
and then go back ito HxD
and then you should be able to press Ctrl+V to paste all the values
it should do this
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_28.webp){:.centered-img}
if you get the following error, it means you've copied the wrong amount of data from your Excel (either too much or too little)
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_29.webp){:.centered-img}
if you did it right, no errors will appear, and it'll just be a clean paste
assuming you succeeded here, save your changes
you may build your ROM at this point; do not be alarmed at what you see

as you can see, the sequence has now been altered, but we haven't completely switched nWo White and nWo Red yet
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_30.webp){:.centered-img}
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_31.webp){:.centered-img}
nWo White still has 9 people in it
and nWo Red still has 6 people in it
now we apply the previous lesson to complete the exercise
to visualize the changes i want to make, I switch the names in both columns:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_32.webp){:.centered-img}
Remember: the "8003A1EC" must never change
as that's where the actual roster in its entirety begins
this is where we'll direct our attention to for now
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_33.webp){:.centered-img}
we only want 5 people in the first stable (nWo White), so we change that to 0005, and for the second stable (nWo Red), we want 9 people, so we change that to 0009
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_34.webp){:.centered-img}
Now, search for "8003A1EC" in HxD again

these should be the only changes you make in your ROM at this stage
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_35.webp){:.centered-img}
save in HxD and then build your ROM again in VPW Studio
this turned out okay
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_36.webp){:.centered-img}
this did not
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_37.webp){:.centered-img}
now this comes into play
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_38.webp){:.centered-img}


you'll notice "8003A20C" gets you to Scott Hall
Hogan is 3 slots behind
recall that every wrestler is worth 4 bytes
subtract 1 slot = 8003A208
subtract 2 slots = 8003A204
subtract 3 slots = 8003A200
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_39.webp){:.centered-img}
make that change accordingly in HxD:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_40.webp){:.centered-img}
save in HxD and then build your ROM again in VPW Studio
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_41.webp){:.centered-img}
I think that's enough for today
If you're having trouble with the second exercise today, please reply to this message and not the one from the first exercise
Once you're able to do these kinds of roster adjustments, you have the foundation to do more interesting things, so I hope you take the time to get the hang of this before we proceed to the next part

### Lesson 4

Alright, here's the last lesson for this module
Today's the day we do cool shit™
but I do not recommend you try this part without fully understanding the first three lessons
What we're going to do today is make one of the removed managers available for selection in the regular roster
this same principle can be used to make any of the normal managers playable, but I don't suggest doing that just yet, as we haven't yet covered lessons relating to editing wrestler data
Additionally, for the sake of allowing you to revisit this lesson without having to do the first three lessons, I'll be using a clean ROM, meaning that nWo White and nWo Red are as they are in vanilla Revenge
first, we're going to look at this part of the sheet
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_42.webp){:.centered-img}

observe this very technical schematic of what we intend to do
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_43.webp){:.centered-img}
By moving Sherri, we're causing some serious things to happen
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_44.webp){:.centered-img}
everything highlighted here will have to change
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_45.webp){:.centered-img}

however, in my experience, changing any of the "Cruiserweight" stables (read: the Manager stables) causes issues, so I recommend not touching those ever
no one can see them anyway
So the very first thing you'll do is, in nWo Red you'll change 0005 to 0006 (as there are now 6 wrestlers in the stable, not 5)
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_46.webp){:.centered-img}
now here's where it gets rough
you won't have to change nWo Red's starting wrestler address (8003A210)
but everything afterwards is going to have to adjust by one wrestler
meaning you have to add 4 bytes
So the Flock, for example, will go from 8003A224 to 8003A228 (add 4 bytes to move forward by one wrestler)

Before we commit to making changes on that scale though
we must avert our attention to the sequence of the roster
we have to physically move Sherri from her current position to the end of the nWo Red stable
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_47.webp){:.centered-img}
do a quick check of the wrestler address column to check you have 90 values (starting from Hogan)
now, as you did in the previous lesson, search for Hogan's wrestler address
select the entire block
and copy your wrestler address column into it
save in HxD and build in VPW Studio

now you'll notice Sherri's not here
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_48.webp){:.centered-img}
because we haven't effected the stable changes yet
but if you go to the Flock...
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_49.webp){:.centered-img}
So yes, big reveal: the Sting from the intro is in fact just Sherri
Woman is the truck driver, Jackreen is the Crow Sting with the bat who confronts the driver, and Sherri is the Wolfpac Sting that confronts Hogan at the end
RED, WHITE, and DRIVER currently serve unknown functions and will crash your game unless you change their wrestler blocks (a lesson for another day)
coming back to the task at hand
Let's look at this again:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_50.webp){:.centered-img}
we'll first change the 0005 to 0006 in-ROM, just like our spreadsheet says
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_51.webp){:.centered-img}
save and build your ROM
Sherri's in the correct spot now:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_52.webp){:.centered-img}
but is also still here:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_53.webp){:.centered-img}
we now have to change this value:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_54.webp){:.centered-img}

that value becomes 8003A228
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_55.webp){:.centered-img}
Save and build your ROM
Raven's now back where he's supposed to be
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_56.webp){:.centered-img}
but then you move to the next stable and you begin to see the road ahead of you
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_57.webp){:.centered-img}
Fortunately, you won't have to adjust any more stable counters; the only one you had to make was to increase the capacity of nWo Red to 6 wrestlers
but you wil now have to add 4 bytes to every wrestler address
there's not really any way to demonstrate this without taking a video
and I don't want to do that because I'm lazy
but for your reference
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_58.webp){:.centered-img}
these are the values you'll need to have in order for Sherri to be in your roster without impacting any other stable

In-ROM:
![Screenshot](../../assets/img/{{ page.assetid }}/{{ page.assetid }}_59.webp){:.centered-img}
after entering these values, saving in HxD and building in VPW Studio
Sherri's there without the need for cheats
but the more relevant application for making Sherri playable
is that Sherri now represents a character that you can customize
with custom movesets
a new costume
etc. etc.
Now that we're at the end of the module, you should now be able to:
1) Change the size and order of each stable
2) Change who's in each stable
3) Make unplayable characters playable
