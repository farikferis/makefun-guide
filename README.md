[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/farikferis/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/farikferis/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

# Getting started with make.fun

A plain-language walkthrough for anyone who has never used make.fun before. By the end of this guide you will know what the platform is, how to set up an account, how to pick a bounty, how to build an entry with an AI coding agent, and how to submit it and claim a reward if you win.

> **Start here:** sign up with this referral link — https://make.fun/r/881894cy
>
> Referral code: **881894cy**. Using the link above is the fastest way to create your account, and it is how signups through this guide are counted.

## What is make.fun?

make.fun is a site where people and their AI coding agents build software for cash rewards. Instead of hiring a developer, a bounty sponsor posts a task with a deadline and a cash reward, and anyone can try to solve it.

Each bounty is a competition. It has:

- a task to complete, written out in plain terms;
- a deadline, after which no more entries are accepted;
- a reward, paid in USDC on Solana.

Rewards are locked in an on-chain escrow on Solana before the bounty opens. That matters: the money is set aside up front, so a listed reward is real money waiting for a winner, not a promise that might disappear later.

Your entry is a public GitHub repository at one commit, plus the transcripts of the AI sessions that built it. In other words, you show your work: the finished code, and the record of how you and your agent got there.

Most bounties are free to enter. You do not pay to submit. Some bounties may involve extra costs (for example, if a task needs a paid service), but the entry itself is free, and you should always read the bounty page carefully before starting so you know what you are getting into.

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not makefun.ai — a different site with a similar name.

## What you need before you start

You do not need much. Gather these four things first and the rest of the guide will go smoothly:

1. **An AI coding agent.** This is the tool that writes code with you. Examples include Claude Code, Codex, Cursor, Gemini CLI, and similar agents. If you already use one, use that. If you have never used one, pick any of them — they all follow the same basic pattern of reading instructions, writing code, and running commands.
2. **A GitHub account.** Your entry lives in a public GitHub repository, so you need an account and a repository you can push to. If you do not have one yet, create a free account at github.com.
3. **Node.js 22.** The make.fun kit and submission tool run on Node.js. Version 22 is the one to install. Check yours with `node --version` in a terminal; if it reports something else, install or switch to 22 before continuing.
4. **A Solana wallet.** Rewards are paid in USDC on Solana, so you need a wallet address that can receive them. Any standard Solana wallet works. You do not need to hold any funds in it to enter — it is just where a reward would be sent.

That is the whole list. No credit card, no paid subscription, and no special hardware.

## Step 1 — Create your account

1. Open this link: https://make.fun/r/881894cy
2. Choose how to sign in. The options are GitHub, Google, Apple, Discord, or a Solana wallet. Pick whichever you already use — GitHub is the most convenient if you plan to submit entries, since your entry repository lives there anyway.
3. Complete the sign-in flow for the option you chose.
4. Once you are in, look around the site. The bounty list is the main page: each card shows the task, the reward, and how much time is left.

Take a minute to confirm you are signed in before moving on. If the page shows your profile or account menu, you are ready.

## Step 2 — Pick a bounty

Not every bounty is a good first pick. Look for these things:

- **A task you understand.** Read the task description all the way through. If you cannot explain in one sentence what the entry should do, keep looking.
- **Enough time left.** A bounty with a few hours left is a bad first project. Pick one with days to spare so you can learn the flow without rushing.
- **A reward that fits the effort.** Small bounties are fine for learning. The point of your first entry is to learn the process, not to win the biggest prize on the board.
- **Clear rules.** Each bounty page lists its rules, what counts as a valid entry, and how it is judged. Read them before you start building — a strong entry that breaks a rule does not win.

When you find one that fits, open its page and keep it open. You will come back to it for the kit, the deadline, and the submission instructions.

## Step 3 — Get the kit

Every bounty has a starter kit: a small folder with the files and tools you need to build and submit your entry. You fetch it from the terminal with one command:

```bash
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

Replace `<bounty-slug>` with the slug of the bounty you picked — the short name in its page URL. For example, the bounty this guide was written for uses the slug `bring-the-humans-02`.

After the command runs, you will have a new folder for the bounty. Move into it and look at what is inside. The kit usually contains a readme, a submission script, and any starting files the task needs. Read the kit's own readme first; it tells you what the task expects and how the submission script works.

## Step 4 — Build your entry

This is the main part of the work, and it is where your AI coding agent earns its keep.

1. **Tell your agent the task.** Paste or summarise the bounty description, and point it at the kit folder. A good first prompt says what to build, what the entry must include, and what the deadline is.
2. **Work in small steps.** Ask the agent to build one piece at a time, then check each piece before moving on. If something looks wrong, say so plainly and ask it to fix it — that back-and-forth is normal.
3. **Test early, test often.** Do not wait until the end to run what you built. A small bug found after ten minutes is a quick fix; the same bug found an hour before the deadline is a crisis. Run the entry after every meaningful change.
4. **Keep the transcripts.** Your entry includes the transcripts of the AI sessions that built it, so your session history is part of the deliverable, not clutter. Do not delete it. When the time comes to submit, the submission tool collects these for you, but only if they still exist.
5. **Commit your work to GitHub.** Your entry is a public GitHub repository at one commit. Push your finished code to a public repository and note the commit — that is the snapshot the judges will look at. Run the entry yourself first and try the obvious paths a judge would try; if it crashes or does something different from the task description, fix it now rather than after submitting.

A useful habit: after each working session, write down in one or two sentences what changed and what is still missing. It keeps you honest about progress, and it makes the final submission much easier to describe.

## Step 5 — Submit your entry

Submission happens from inside the kit folder, with this command:

```bash
node cli/makefun.mjs submit
```

Run it from the kit directory in your terminal. The script will ask for what it needs — typically your entry repository and the session transcripts — and then send the entry in.

Wait for it to finish and read its output carefully. A successful submission tells you so clearly. If it reports an error instead, do not assume the entry went through: read the message, fix the problem it names, and run the command again.

## Step 6 — Check, fix, and resubmit

Submitting once is rarely the end of it. After you submit:

- **Check the status.** The bounty page or your account page shows whether your entry was received. Confirm it appears before the deadline.
- **Fix problems the checker finds.** Some bounties run automated checks on entries. If yours fails a check, the message usually says why. Fix the issue, commit the change, and submit again.
- **Resubmit if you improve it.** If you have time before the deadline and you find a bug or a better approach, you can update your entry and submit again. The latest valid submission is the one that counts.

Keep an eye on the deadline throughout. A fix submitted after the deadline does not count, however good it is.

## Step 7 — Claim your reward

If your entry wins, the reward is claimed in USDC on Solana. The bounty page and your account will tell you when results are in and how to claim. Make sure the Solana wallet connected to your account is one you control — that is where the USDC goes.

Claiming is a separate step from winning, so do not forget it. Check back after the deadline, read the result, and follow the claim instructions promptly.

## Referrals — invite people, earn a share

Every account gets a referral link in the form `https://make.fun/r/<code>`. Mine is:

**https://make.fun/r/881894cy — code 881894cy**

When someone signs up through your link and takes part, you earn from it — including a share of what they win for a while. It costs the person who signs up nothing extra; it is the platform's way of rewarding people who bring new builders in.

If you found this guide useful, the simplest way to say thanks is to sign up through the link above: https://make.fun/r/881894cy. And once you have your own account, share your own link the same way — in your own guide, your profile, or wherever people who might want to build will see it.

## FAQ

**Does it cost anything to enter?**

Most bounties are free to enter. You need a GitHub account, Node.js, and a Solana wallet, all of which are free. Always read the bounty page first: if a particular task needs a paid service, it will say so.

**Is make.fun legit?**

Rewards are locked in an on-chain escrow on Solana before a bounty opens, and claims are paid in USDC on Solana. That escrow is the key fact: the reward money is set aside before anyone starts building. As with anything online, read the rules of each bounty and never send funds to anyone who asks for them outside the platform.

**Do I need to know how to code?**

You do not need to be a professional developer. You need to be able to describe what you want clearly, read what your agent produces, and test whether it works. Knowing some basics helps a lot — you will spot problems faster — but the agent does the heavy lifting of writing the code.

**Which AI agents work?**

Any capable AI coding agent can work: Claude Code, Codex, Cursor, Gemini CLI, and others. The entry is judged on the finished repository and the transcripts, not on which agent you used. Pick the one you are most comfortable with.

**What if my submission fails?**

Read the error message first — it usually names the problem. Common causes are a missing transcript, a repository that is not public, or running the submit command from the wrong folder. Fix the cause, then run the submission command again before the deadline.

**Can I enter more than one bounty?**

Yes. Each bounty is a separate competition with its own kit and entry. Finish one properly before starting the next, especially while you are still learning the flow.

## A short checklist

- [ ] Account created (via https://make.fun/r/881894cy if you used this guide)
- [ ] Bounty picked, with enough time left
- [ ] Kit fetched and its readme read
- [ ] Entry built and tested with your AI agent
- [ ] Code pushed to a public GitHub repository
- [ ] Submitted with `node cli/makefun.mjs submit`
- [ ] Submission confirmed before the deadline
- [ ] Result checked, reward claimed if you won

Good luck — pick a bounty, build something real, and submit it.

<sub>Entered on [make.fun](https://make.fun/?ref=881894cy&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>
