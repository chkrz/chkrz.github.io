---
layout: post
title: "LLMs in Finance: First, Ask if the Task is Well-Defined"
date: 2026-06-21
lang: en
ref: llm-finance-well-defined
---

With LLMs having proven wildly successful in the coding domain, the industry is naturally turning its attention to other arenas, hoping to trigger the same kind of chemical reaction. The most hyped frontier right now is Finance.

Recently, there has been a flurry of activity: [Anthropic highly publicized their Finance Agent framework and applications](https://www.anthropic.com/news/finance-agents); rumors surfaced prior to that indicating [OpenAI hired a large number of investment bankers to help train models](https://www.afr.com/companies/financial-services/openai-hires-100-investment-bankers-to-train-its-ai-20251022-p5n4er); and top Chinese foundational model startups are aggressively following suit, launching various "Fellow programs" to recruit industry experts.

But behind all this buzz, I have a lingering suspicion: everyone might just be collectively eyeing finance as the closest "fat piece of meat" to the money, without having a clear answer to "what exactly are we doing?" and "is this path fundamentally viable?"

## Why Coding Worked

Let's look back at an indisputably successful scenario: Coding.

It is now widely accepted that LLMs are genuinely capable at writing code—it's not just a gimmick. Many attribute this to the massive amount of code data available or the models simply getting smarter. However, I believe the core foundation is actually this: **Coding is an extremely well-defined task.**

Much like the breakthroughs achieved by AlphaProof and o1 in mathematical reasoning, domains that can take off during the RL (Reinforcement Learning) phase generally meet two prerequisites:

First, **there must be a relatively objective metric/reward that is hard to hack.**
With code, it either runs or it doesn't. It passes the test cases, or it fails. It's binary, making it very difficult for the model to "play dumb" and bluff its way through. Similarly, mathematical proofs have rigorous formal verifiers. This kind of inherently clean reward signal is the prerequisite for spinning up the RL flywheel.

Second, **there must be an off-the-shelf, low-cost test environment.**
Code has interpreters and execution environments; you can run it thousands of times practically for free. Math has verifiers. This means the model can continuously trial, error, receive feedback, and iterate within the environment. It is also the prerequisite for automated data generation and evaluation.

When both conditions are met, the feedback loop closes, and the Scaling Law can truly flex its muscles in the post-training phase.

## Are Finance Tasks Well-Defined?

Following this logic, let's dissect the currently hyped financial scenarios. Do they meet these two conditions?

Let's start with **Investment Banking (IBD)**. Investment banking actually involves a massive amount of paperwork—Pitch Decks, Due Diligence reports, and various Memos. This type of work generally follows fixed templates and narrative structures. Using LLMs here definitely boosts efficiency, but it functions more as an advanced writing assistant rather than "intelligent decision-making." More critically, this task lacks a clear metric. What constitutes a "good" Pitch Deck? Ultimately, it's a subjective call by an MD (Managing Director). You simply cannot evaluate it automatically, which naturally rules out large-scale RL training.

Next is **Sell-side Research**. The core logic of the sell-side is digesting huge volumes of information, organizing the logic, and ultimately issuing a Buy, Sell, or Hold recommendation. At first glance, using stock price movements as feedback seems viable. But the reality is that whether a research report's logic is sound is a highly subjective and long-term judgment. If you use the predicted stock's one-week performance as your metric, the macro and sentiment noise is overwhelmingly loud. It is impossible to verify the true reasoning ability of the model over the short term.

What about **Buy-side Investment** (Discretionary Long-Only)? This task certainly has clear metrics, such as absolute return or the Sharpe ratio. But it dies on the second condition: it is extremely difficult to build a reliable Test Environment. The financial market is a one-time game; it's not a sandbox where you can reboot and run an Agent at zero cost. If you perform RL on historical backtests, the first thing the model learns isn't how to make money, but how to "Reward Hack"—using overfitted historical data to fool the reward function. Human quantitative funds have been banging their heads against the wall trying to prevent overfitting for decades; merely tossing an LLM into the mix won't miraculously untie this knot.

## The One Exception: Alpha Factor Mining

However, amidst the fog, I believe there is one narrow path that might lead somewhere: letting LLMs act within a quantitative framework to **mine Alpha factors**.

Mining factors surprisingly aligns perfectly with the two conditions mentioned above.
First, the test environment is already built. Quant firms naturally maintain extremely robust Backtest engines that calculate IC (Information Coefficient), turnover rates, and more. These can be used directly as the LLM's Environment.
Second, its metrics are clear and possess somewhat anti-hack characteristics. IC and Sharpe can be precisely quantified. As for overfitting, the quant industry established strict defenses long ago: heavy turnover penalties, rigorous Out-Of-Sample (OOS) testing, and Walk-forward analysis. Though these rules weren't originally designed for AI, they perfectly restrict LLMs from pulling fast ones.

Therefore, using LLMs to mine factors is viable not because they truly "understand" macroeconomics or can accurately read financial statements. It works because "finding statistical patterns and writing them as executable operators" is—given existing quant infrastructure—a well-defined engineering problem.

## Final Thoughts

Right now, everyone is asking: Can we train an LLM that understands finance better?
I feel the angle of this question is slightly off. Instead, we should take a step back and ask: **Have we clearly defined this specific financial task?**

If it's a job where even humans have to rely on "feel" and experience, then the LLM's ceiling is likely just an advanced efficiency tool. It won't bring about a leap in capability boundaries.

Rather than painting big pictures over ambiguous business scenarios, we'd be better off searching for the next "sandbox" that can form a closed-loop training cycle and naturally constrains cheating. After all, outside of code and mathematics, tasks in the real world that possess both clear metrics and reliable test environments are truly few and far between.