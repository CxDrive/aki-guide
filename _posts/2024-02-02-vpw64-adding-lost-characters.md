---
layout: post
author: RagDas
date: 2024-02-02
title: Adding Lost Characters + Great Nita vs. Mr. Pogo (VPW Studio Test Hack)
slug: adding-lost-characters
description:
category: vpw64
category-title: Virtual Pro Wrestling 64
tags: ["vpw64"]
source: YouTube
source-url: https://www.youtube.com/watch?v=ngGnjD9eKnY
assetid: 98e02637
ogp: true
published: true
---


<div class="ratio ratio-16x9 w-75 mx-auto d-block">
  <iframe src="https://www.youtube.com/embed/ngGnjD9eKnY" title="YouTube video" allowfullscreen></iframe>
</div>


### Video Description


> (Reuploaded because I solved one of the errors I wrote about in detail in the previous upload -- also sorry for the jitters in the footage, I try to avoid knocking P2 out of the ring where possible to avoid it).
>
> Before continuing, credit to RyanCE on FireProClub some time in 2009 or prior for posting that thread that introduced the unused characters in VPW64 to me. Secondly, credit to freem for being the first to show what the default costumes for said character looked like. This video is just the next evolution of what came before: actually ROM hacking those characters into the game for use.
>
> What you see in this video was an experiment to test the principle of creating roster slots using what I'm currently dubbing the "Nameless Man" method. I proved this with Revenge earlier this week, but while roster slots are limited in quantity without a decomp, any address (within reason) can be used to occupy a roster slot, so long as the first three bytes are an ID4 (2 bytes) and an ID2 (1 byte). The result, if there is no Wrestler Block to house all the necessary details of a wrestler's profile, is a "Nameless Man" that exhibits whatever information is contained elsewhere in the ROM corresponding to that wrestler's ID4.
>
> In this case, we're taking VPW64's fabled "dummy" characters and ROM hacking them into the game. Like World Tour, prior to the actual roster addresses starting, there are four addresses that appear that don't appear to do anything (it's unclear what they're there for):

    800487BC
    800487C8
    80048808
    80048814

> Given that these are entirely unused, I found small pockets of 3 bytes that existed within DDP's and someone else's Wrestler Blocks (don't know who -- whomever comes before DDP in-ROM in Wrestler Blocks), wrote in the ID4s for Great Nita and Mr. Pogo, and further supplemented them with ID2s that don't exist (values past Syxx's ID2, who serves as the last character in-ROM). The result is what you see in the video.
>
> Right off the bat, Syxx dons a yellow version of Keiji Mutoh's attire, with costume values completely out of whack. He retains his moves, but his name now, confoundingly, reads from what I think is DDP's height and weight data (only seen during ring intros). Also confoundingly: there seems to be some invisible link between Yoshiaki Fujiwara and the two wrestlers that were added. All three share the same long name data and appearance data. Changing one will change the same for the other two. Thus, the best you can get in this scenario is a match with Nita and Pogo where you see the former's P1 costume and the latter's P2 costume; no other data seems to exist nor be changeable in any meaningful fashion, aside from movesets and params — I modified these such that Nita uses Onita's moveset and params, and Pogo uses Tiger Jeet Singh's moveset and params.
>
> My conclusion is that the Nameless Man method feels like a stopgap solution for adding wrestlers to the roster without a decomp. I don't think it has any meaningful application after Revenge, and even within the scope of these first three N64 games, I'm not so sure people would be satisfied with something like this given its potential to cause unforeseen issues. I know for a fact this is more trouble than its worth in VPW64, so I'm 100% not pursuing it. I have yet to observe serious issues beyond the 'shared slot' nature of the Nameless Men in Revenge. Time will tell.
>
> -- <cite>[@RagDas01](https://www.youtube.com/@RagDas01)</cite>
