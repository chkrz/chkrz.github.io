---
layout: post
title: "I Need a War Room, Not a Chat Window"
date: 2026-04-26
---

I'm an algorithm engineer. My work spans training language models and building AI-powered applications -- designing experiments, submitting training jobs to GPU clusters, developing multi-agent systems, shipping features. I usually have multiple projects running in parallel, each with its own context, configs, and deadlines.

Here's what I've learned: since AI coding became real -- and it has, this is a genuine productivity revolution -- the bottleneck has never been the AI. It has always been me. The human in the loop. Every iteration of my workflow has been about one thing -- removing myself from the critical path.

## The Loop

Let me walk through how this played out, using model training as the example -- because that's where I live.

**Loop 0**: Everything manual. I write training scripts, configure experiments, submit jobs, watch logs, debug CUDA errors, analyze results, write reports. Concurrency: maybe 1-2 projects, if I context-switch aggressively.

**Loop 1 -- the "vibe coding" era**: AI writes code with me. But I'm still manually submitting training jobs, checking GPU utilization and loss curves, downloading logs when a run crashes, feeding errors back to the AI, fixing configs, resubmitting, waiting, analyzing results, updating docs. The AI helps with each step, but I'm the one driving every transition. The real bottleneck: job monitoring, failure debugging, and results analysis -- all require me to be actively present.

**Loop 2 -- where I am now**: AI runs entire experiments end-to-end. I give it requirements and a spec, it writes the plan, submits jobs, monitors progress, fills in documentation. But I still need to push it forward when it drifts, align context when it gets confused, and validate results I don't fully trust yet. Concurrency: maybe 3 projects. The bottleneck has shifted from doing the work to managing the AI doing the work.

**Loop 3 -- where I want to be**: I analyze requirements and write specs. AI handles everything else with trustworthy results. Concurrency: 10 projects. The bottleneck becomes managing multiple AI teams and aligning with other humans.

**Loop 4 -- where it's heading**: I'm out of the loop entirely. What remains isn't a team -- it's a society. AI agents operate under shared structures and incentives, something closer to an economic system than a management hierarchy. Think capitalism for AI: competition, resource allocation, value exchange -- not because someone is directing each agent, but because the system's rules produce useful outcomes. The human role shifts from manager to legislator: designing the system, not running it.

Notice the pattern. Each stage removes more of me from the loop. But at every stage, whatever human involvement remains becomes the new bottleneck.

## Chat Has Run Its Course

Here's the problem: the tools assume Loop 1.

The dominant interface is still a conversation. A terminal chat. An IDE sidebar. Sure, you can run multiple agents in one window, or split them across tabs. Tools like Claude Code already support this. But the interaction model is the same: linear threads you have to manually switch between and keep track of in your head.

Cursor's success proved that the right interaction paradigm matters as much as the underlying model. It nailed the best interface for the copilot era -- AI embedded in the editor, paired with the developer. That was the right answer for Loop 1.

But I'm not in Loop 1 anymore. I'm not pair programming. I'm managing. I set direction for three different agent sessions, each running for hours, each accumulating context I can't hold in my head. I'm constantly switching between terminal tabs, scrolling through histories, trying to remember: did I ask it to fix that test? Did it finish the monitoring setup? Which experiment group is running?

The chat paradigm isn't wrong -- it's outdated. And the question now is: who will nail the next interaction paradigm?

## What I Actually Need

What does managing a team of workers look like? Not sitting in one long conversation with each of them. It looks like:

- A **dashboard** showing all active workstreams and their status
- The ability to **drill into** any project for details
- **Asynchronous progress** -- work moves forward without me watching
- **On-demand messaging** -- I ping an agent when I need to steer, not the other way around
- **Alerts** -- the agent pings me when it's stuck or done, not when it wants to chat

That's the interface I need. Not "open a terminal and start chatting." A project management view with integrated messaging. I see all my agents, what they're working on, where they're blocked. I jump in when needed. I stay out when not.

OpenAI's [Symphony](https://github.com/openai/symphony) points in this direction -- its own tagline says it all: "manage work instead of supervising coding agents." Multiple agents, orchestrated, with a human overseeing the system rather than driving each one keystroke by keystroke. It's not a chat interface -- it's a control plane.

## The Real Constraint

The missing piece isn't a smarter model. Models are already good enough to run experiments, write docs, and debug autonomously. What's missing is the management layer -- the tool that lets one human coordinate many AI workers without becoming the bottleneck again.

Every time we reduce human-in-the-loop for one part of the workflow, the remaining human involvement becomes the new constraint. Right now, that constraint is the overhead of managing AI itself. The irony: we need AI project management tools to manage AI workers, so that the human can finally step back far enough to think about what actually matters.

We're managing a team through walkie-talkies. Give me a war room.
