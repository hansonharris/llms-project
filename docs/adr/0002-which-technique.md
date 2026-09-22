# ADR-0002: Which prompting technique will I use when consulting my model?

**Status:** Proposed | Accepted | Superseded by ADR-00X
**Date:** 2026-09-22

## Context

I am building an LLM project for troubleshooting heat pump systems. I need to choose a prompting technique in order to get the best use out of the model i create for my specific purpose.

## Decision

I chose to use the Self-Verification technique. This technique has the model generate multiple possible solutions. It then has the model score each solution based on masked versions of the original prompt to choose the best course of action. This is useful in troubleshooting because it often involves multiple possible paths to try. Using this technique, the model weighs each path and chooses which it believes is best. This is exactly how humans reason through troubleshooting and why I believe it is the best of the three techniques I have considered.  

## Alternatives considered

Thread of thought: This technique works well when dealing with question-answering and retrieval settings especially for large, complex problems. This would benefi my project because troubleshooting is naturally full of questions and often needs to have data retrieved for context. I did not choose this technique ultimately because it lacks the affordance of weighing multiple paths carefully like Self-Verification does.

Tree of Thought: This technique starts with an initial search problem and produces multiple possible steps forward. It evaluates the progress each step makes and decides which step to take next. This would be particularly useful in my project because troubleshooting is often an evolving process where a discovery could alter the course of action. I ended up not choosing this technique because I felt like Self-Verification is a safer option when dealing with troubleshooting because it checks its solution at the end against a masked prompt. 

## Consequences

A consequence of my decision is the fact that I only chose one prompting technique. However, slightly different needs from my model could benefit differently from different prompting techniques. If I go back and change my decision, it will likely be to use a combination of prompting techniques. 
