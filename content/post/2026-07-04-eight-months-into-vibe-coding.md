---
title: "Eight months into vibe coding"
author: Yue Jiang
date: '2026-07-04'
slug: eight-months-into-vibe-coding
categories: []
tags: ["coding agents"]
---

Since last winter, I started using Claude Code, then Codex, for my work — my current setup is a
Claude Max 5x + ChatGPT Pro. They quickly became something I reach for every day. Below are a couple
of notes on customizations I've picked up along the way. The first two are for VS Code — I know the
CLI is where the bleeding edge lives and is the best supported, but for the analysis work I do I
prefer being able to quickly interact with files and plots (usually on a remote EC2 instance).

## Seeing what the agent makes in real time

A lot of my work is data analysis, which means plots. When an agent is running on a remote box,
there's an annoying gap between "it made a figure" and "I can actually look at it." So I put together
a tiny markdown-based [canvas](https://github.com/Yue-Jiang/agent-misc/tree/main/canvas) that the agent writes plots
into, so they show up live while it works — no heavy tooling, just a text file and a preview pane.

## Knowing which window needs me

I usually run several agents at once across different VS Code windows — often over SSH to different
machines. Sometimes I'd miss a window that's asking me to approve something or needs my input. I
wrote a little [menubar monitor](https://github.com/Yue-Jiang/vscode-claude-monitor) that watches all
the windows and shows a colored dot when one hits a permission prompt or ends on a question, plus
hotkeys to jump straight to it. It turns "check every window" into "glance at the menubar." I've also
shifted to using "auto" mode in Claude Code and "Approve for me" mode in Codex, which seem to strike a
good balance between asking for permission every single time and going rogue and breaking things.

## Onboarding a larger audience to compute resources

With some reflection, it feels to me the current biggest bottleneck — after coding agents largely
solve coding (and Claude Science solves a lot of computational biology reasoning) — is that not
everyone has access to the compute resources needed to perform heavy tasks. Most scientists around me
have the knowledge about the biological question, the help from coding agents to set up bioinformatics
pipelines, and usually better judgment than me to evaluate the analysis outcome. But in most places
I've worked, computing resources are generally restricted to the computational department, which
seems to be the bottleneck as of summer 2026. So, without going into too much detail, I pulled
together the cloud setup documentation and worked with Claude to consolidate it into skills. The end
product is something scientists point their local Claude Code app to, then watch it go through the
steps to set up their instance, connect to storage for input files, and publish results. Nothing
crazy, but this route of writing the setup docs to be **executed by an agent on their behalf** is
pretty useful — a scientist can have an instance up and running, analysis-ready, within 10 minutes.
