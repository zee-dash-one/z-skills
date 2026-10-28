---
name: plan-and-breakdown
description: >-
  Use when a feature, fix or technical goal must become a short spec plus
  ordered, testable tasks (usually .todo/ files for a local Cursor to execute).
---
# Plan and breakdown

Goal: the smallest plan that can be verified. A spec precise enough to replace tests is just a program written in prose; put precision into acceptance checks instead.

## Steps
1. Read context first: the repo's AGENTS.md (or README) and only the target files. Do not scan the whole repo.
2. Write a mini-spec (max ~15 lines): goal, scope, out of scope, risks, decisions still open for the user.
3. Write the verification plan before the tasks: which test, command or observable result proves each part works. Every feature gets a test; every bug gets a regression test.
4. Break into tasks that are small, ordered and independently verifiable (one concern per task, dependencies explicit).
5. If the work runs on the user's machine or server, write the tasks as `.todo/NN-name.md` files following the `instrucoes-para-cursor-local` skill, including: the done-file rule (when finished, move the task from `.todo/` to `.todo/.done/`, never delete; `00-LEIA-ME.md` stays), Status, Objective, Prerequisites, Steps with exact commands, Acceptance, After, and the signature.
6. Before creating tasks in a repo that already has active `.todo/` files from another assistant, coordinate with it first.
7. Write code, commands and comments in English unless the repo already uses another language.
8. Deliver: 3-6 lines in chat with the file paths and which task to run first.
