---
title: "Learning with Claude: Implementing a transformer from scratch"
author: Yue Jiang
date: '2026-07-15'
slug: transformer-implementation
categories: []
tags: ["deep learning"]
---

I tried to use Claude Code for self study. Starting here with a 10-ish day [tutorial](https://github.com/Yue-Jiang/transformer-tutorial) on implementation of the GPT-style transformer model. This was an enjoyable experience - after a few days I got to implement embedding, layernorm, multi-head attention, cross entropy and put them together into a decoder-only transformer that actually trains on my laptop. Beyond learning about transformer implementation, I realized that I could self study other subjects this way too - it will likely be more pleasant and motivating - feels a bit like Duolingo. I wish I had coding agents like this back in college and grad school (Maybe now is the time to revisit that measure theory class I struggled with most! or not). The tutorial itself may not be very useful for other people, although a couple observations may generalize. When using Claude for self study, I find it helpful to 1) talk with it, be explicit about my understanding, assumptions and confusions 2) have it break the learning down to bite size 3) use a plain text editor for assignments - even VS Code Copilot autocompletion implements transformers better than me.

The main reason for writing this post is actually to make note of something else. Without prompting, Claude also generated a short corpus for testing the training step, which I quite like:

> the little robot woke at dawn and checked its battery. the battery was full, and the day was new. the little robot rolled to the window and watched the sun climb over the hills. every morning the robot made the same plan: water the garden, count the clouds, and write one line in its journal.
>
> the garden was small but proud. the robot watered the beans, the peas, and the one stubborn tomato that never turned red. "grow," said the robot, "grow and be red." the tomato said nothing, because tomatoes do not talk, but the robot liked to believe it was listening.
>
> the clouds were harder to count. some clouds drifted apart while the robot counted them, and some clouds joined together, so the number was never the same twice. the robot wrote the number down anyway. numbers did not need to be perfect to be worth keeping.
>
> in the journal the robot wrote small true things. "today the wind came from the west." "today the beans grew one finger taller." "today i counted nine clouds, or maybe eight." the journal was full of days, and every day was a little different and a little the same.
>
> one morning a bird landed on the fence and watched the robot water the garden. "you do the same thing every day," said the bird. "does it not get old?" the robot thought about this while the water ran. "the days repeat," said the robot, "but the garden does not. the beans are taller than yesterday. the clouds are new clouds. even the sun climbs a slightly different sky."
>
> the bird hopped along the fence. "i fly somewhere new every day," said the bird, "and it all starts to look the same. maybe new is not about where you go. maybe new is about how you look." the robot nodded, because that was a small true thing, and small true things belonged in the journal.
>
> so the robot wrote: "today a bird taught me that the same garden, watched closely, is never the same garden." then the robot watered the stubborn tomato one more time, just in case. "grow," said the robot, "grow and be red." and high on the vine, where the sun touched it first, the tomato had started, just barely, to blush.
>
> the seasons turned the way seasons do. the beans climbed their poles and the peas filled their pods, and the robot counted clouds through the summer and into the fall. the bird came back most mornings, and they argued in a friendly way about whether counting clouds was useful. "the number is always wrong," said the bird. "the counting is the point," said the robot. "the number is just what the counting leaves behind."
>
> when the first frost came, the robot picked the tomato, red at last, and set it on the windowsill where the sun could see what it had done. the journal got a whole page that day: "today the stubborn tomato was red. it took the whole summer. some true things are slow." the bird ate half the tomato, which the robot decided was also a kind of sharing, and the garden slept, and the robot wound its journal back to the first page, and began again.

Later I asked about it and to my surprise, it provided thorough reasoning about how it generated the story. I find it impressive it can generate a good story with all the practical considerations.

![Claude explaining how and why it wrote the training corpus](/img/transformer-comment.png)

And on the last day, after I completed the tutorial, it said: 

![Claude's day-10 "course complete" sign-off](/img/transformer-complete.png)

Now I think I'll remember that 🤖🍅 for a number of years.