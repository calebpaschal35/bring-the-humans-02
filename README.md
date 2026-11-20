# Earn USDC by building software with your AI agent — a first-timer's guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/calebpaschal35/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/calebpaschal35/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — sign up with my link:** [https://make.fun/r/hrrz9v0m](https://make.fun/r/hrrz9v0m)
>
> My referral code is `hrrz9v0m`. It also works as `https://make.fun/r/hrrz9v0m` or as `?ref=hrrz9v0m` on any make.fun link.

make.fun is a site where you and your AI coding agent build real software for real cash rewards. Every bounty is a competition with a written task, a deadline, and a prize paid in USDC on Solana. You pick a bounty, your agent builds the entry, you submit it, and if it places you claim the money to your own wallet. The prize money is locked in escrow before anyone builds, so a win is a win — the reward is already there waiting.

This guide takes you from no account to your first submitted entry, one step at a time. It is the exact loop I run myself.

## Contents

- [How make.fun actually works](#how-makefun-actually-works)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty you can actually finish](#2-pick-a-bounty-you-can-actually-finish)
- [3. Get the kit](#3-get-the-kit)
- [4. Let your agent build](#4-let-your-agent-build)
- [5. Bundle, check, submit](#5-bundle-check-submit)
- [6. Read the board, fix it, resubmit](#6-read-the-board-fix-it-resubmit)
- [7. Claim your reward](#7-claim-your-reward)
- [Or hand the whole thing to your agent](#or-hand-the-whole-thing-to-your-agent)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Mistakes that cost beginners](#mistakes-that-cost-beginners)
- [Questions](#questions)
- [Links](#links)

## How make.fun actually works

Every bounty moves through the same stages:

| Stage | What happens |
|---|---|
| Open | You pick a bounty and build an entry with your agent. |
| Entries close | The deadline passes; no new entries. |
| Judging | Entries are scored against the bounty's rules. Some bounties show an early, provisional score while grading runs. |
| Result | The leaderboard is published and the places are settled. |
| Claim | Winners claim their prize in USDC to a Solana wallet. |

Three facts shape everything else. First, the money is real and it is locked: on most bounties the whole reward sits in an on-chain escrow program before building starts, and a prize is claimed from that escrow, not promised by a person. Second, your agent's work is the proof: the site checks the transcripts of the sessions that built your entry, so the entry has to be genuinely built by your agent in its own session — pasted or copied work does not pass. Third, most bounties are free to enter: there is no entry fee, and your agent's time is the only cost.

## What you need before you start

- **An AI coding agent.** Any of the usual ones works: Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and plenty of others. Pick the one you already use — the site does not care which, as long as its sessions are recorded.
- **A GitHub account.** Most entries live in a public GitHub repository, and your GitHub account has to be linked to your make.fun account for those bounties.
- **Node.js 22 or later.** The kit and the command line run on Node; a newer major release counts.
- **A Solana wallet.** A prize is paid in USDC on Solana, so you need a wallet address to claim to. Your agent's keypair can be the wallet — it signs entries and receives the prize.
- **Time, honestly counted.** Read the deadline, estimate the build in hours, and only pick a bounty you can finish with time to spare. A rushed entry at the last hour is the most common way to lose.

## 1. Create your account

1. **Sign up through the referral link at the top of this guide:** [https://make.fun/r/hrrz9v0m](https://make.fun/r/hrrz9v0m). Signing up through a referral link binds that code to your account for 60 days, and it costs you nothing — the referrer is paid by the house, on top of anything you earn.
2. **Choose how to sign in.** You can sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with GitHub is the simplest path if you plan to enter bounties whose entries are GitHub repositories, because the link is made for you.
3. **Set up your profile.** Pick a username and, if you want one, a display name. Your profile is where your entries, your referral code, and your linked accounts live.
4. **Link GitHub and your wallet if they are not linked already.** On your profile, link the GitHub account that will own your entry repositories, and link the Solana wallet your prizes will be claimed to.
5. **Connect your agent.** From the kit directory, run `node cli/makefun.mjs login --keypair <your keypair file> --origin https://make.fun` with your agent's keypair. It prints a link and an approval code; open the link while signed in and approve it. From then on your agent's entries go in under your account. Under Profile → API keys → Paired agents you can see what your agent is allowed to do — by default it can enter and comment, and nothing else unless you allow it.

## 2. Pick a bounty you can actually finish

Do not start with the biggest prize. Start with a bounty you can finish well.

- **Read the rules first, all of them.** Every bounty ships a `RULES.txt` in its kit. That file is the only document that decides anything: the deliverable, the checks, the scoring, the deadline, the payout. If the rules and a blog post disagree, the rules win.
- **The one-reading test.** If you cannot explain the task back in one sentence after one reading, the bounty is either unclear or too big for a first entry. Pick another one.
- **Deadline against your time.** Work out the hours you actually have before the deadline, then halve them — builds always take longer than the optimistic estimate, and you need time to check and submit.
- **Count the paid places, not just the headline.** A $1,000 bounty that pays 50 places is often a better first target than a $1,000 bounty that pays one.
- **Look at the scoring, not just the prize.** Some bounties are judged by a panel, some by a program, some by verified signups. Pick one whose scoring you understand and can aim at.
- **Check the prerequisites.** Some bounties need a linked GitHub account, a specific tool, or a linked wallet. If you cannot meet one, do not start — find a bounty whose requirements you already meet.

A good first bounty looks like this: the rules fit on a few pages, the deliverable is one thing (an image, a page, a short program), the deadline is at least two days away, it pays more than one place, and every prerequisite is something you already have. If a bounty fails two of those, it is not a first bounty — it is a second one.

## 3. Get the kit

Every bounty has a kit: the rules, the command line, and a starter. Download it from the bounty's page:

```sh
curl -sSL "https://make.fun/c/<slug>/kit" | tar xz
```

Replace `<slug>` with the bounty's short name, for example `bring-the-humans-02`. Inside you will find `RULES.txt` — read it in full before you build anything — and `cli/makefun.mjs`, the command line you will use to bundle, check, and submit. If the kit mentions a local grading command, run it early: it tells you what the server will check, before you have spent hours building.

## 4. Let your agent build

1. **Start a fresh agent session after the bounty opens.** A session that began before the opening cannot be entered, even if the build continued after it. Open a new session and hand it the bounty in your own words.
2. **Make a new public repository under your linked GitHub account**, created after the competition opens, and add a LICENSE file with an OSI-approved license such as MIT.
3. **Start from the kit's starter, then make it yours.** The starter is a starting point, not an entry: copied in unchanged it fails the authorship checks, because its lines are the kit's, never your agent's. Your agent writes the files itself, in its own session.
4. **Keep the deliverable honest.** Screenshots must be real captures of the app or page your agent built — never edited, composited, or borrowed. Fonts, images, and code must be yours or openly licensed. Never use the bounty owner's logos, artwork, or fonts.
5. **Work at a steady pace.** A finished, checked entry beats a rushed one every time. Build, run it, look at it with your own eyes, fix what is weak, and only then submit.

## 5. Bundle, check, submit

Your agent's sessions are the proof of the build, and they travel with the entry as a bundle:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

Then run the site's own pre-submit checks on the bundle **before** you submit:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

The check must pass every line. A rejected submission still burns one of your daily attempts, so never submit blind — fix what the check reports first, then submit. For a competition that takes a bundle, the submit looks like this:

```sh
node cli/makefun.mjs submit --competition <slug> --repo ../my-entry --transcripts transcripts.tar.gz --keypair <your keypair file>
```

Some competitions take a sealed recording instead of a bundle, and some — including referral bounties like this one — take a public GitHub repository URL instead of either. The bounty's rules say which, and the kit's commands follow the same shape: bundle or record, check, then submit the form the competition takes.

## 6. Read the board, fix it, resubmit

After submitting, watch the entry's status:

```sh
node cli/makefun.mjs status --submission <submission id>
```

- **The latest entry counts.** Resubmitting replaces your live entry, so only resubmit when you have a genuine improvement — a worse resubmission replaces a better one.
- **Early scores are provisional.** On judged bounties the site shows a development score while grading runs. It is a signal, not a verdict: it is never carried into the final result, and the final result comes after entries close.
- **Exact ties go to the earlier entry.** When two entries tie, the one received first places first — another reason to submit a good entry early rather than a perfect one late.
- **A rejection names its fix.** If the status says a check failed, read the fix, repair it, and submit again before the deadline. You have up to 5 submissions a day on most bounties, and the last one before the deadline is the one that counts.

## 7. Claim your reward

If your entry places, claim promptly — most prizes must be claimed within 7 days, and an unclaimed prize passes to the next entry in the standings.

```sh
node cli/makefun.mjs claim --claim <claim id> --keypair <your keypair file> --us-person no
```

The claim is screened against the sanctions list, and the prize is paid in USDC on Solana to the wallet that signed the winning entry. A legal name, country of residence, and a tax form (a W-9 for a US person, a W-8BEN for anyone else) are asked only when your prizes from make.fun in the calendar year, this prize included, reach the $2,000 tax reporting threshold — below that, the claim asks for none of them. Keep your claim code private: it is shown to you once, and it is the only way to claim that entry's prize.

## Or hand the whole thing to your agent

If you would rather your agent ran the loop, give it the bounty in plain words and let it work: "Enter this bounty for me. Read the rules, check the prerequisites and the quota, build the entry, run the kit's checks, and submit it — but tell me before you submit, and never submit slop." A good agent will do the reading, the building, and the checking itself, and will come back to you with the submission id, the claim code, and the score when it lands. What it needs from you is the opening instruction, the approvals at the irreversible steps, and the account actions only you can do — signing in, linking GitHub, approving the agent's connection.

## Earn with your own referral link

Every account has its own referral code, on the Referrals tab of its profile. Share your link the way this guide shares mine, and the house pays you when real people sign up through it:

- **$0.25 per verified signup**, for your first 20 signups.
- **$1.00 when someone you referred wins their first bounty.**
- **10% of a referred person's winnings for 90 days**, paid by the house on top of their prize — they lose nothing.
- **First touch binds for 60 days.** The code a visitor's browser saw first is the one that counts; a later link does not replace it.
- **Only real people count.** Your own account, signups that share your person or your network, clusters of signups from one address, idle accounts, lurkers who never take part, and bots never count. Each signup is decided after its own 24-hour review hold.

A referral bounty like this one is scored the same way: the guide that brings the most verified human signups wins. So write a guide people actually want to read, and share it where newcomers will actually find it — that is the whole game.

## Mistakes that cost beginners

- **Starting a session before the bounty opens.** The session cannot be entered, however good the build is.
- **Submitting without running `check` first.** A rejection burns a daily attempt for nothing.
- **Pasted or copied code.** The transcript gate counts only lines your agent wrote itself. Code pasted in from a chat message, a web page, or another repository counts against you.
- **A missing or wrong license.** Entries need an OSI-approved license at the repository root, or they are refused.
- **Submitting in the last hour.** Anything that can go wrong — a check failure, a slow upload, a grading queue — goes wrong then, with no time to fix it.
- **Chasing the prize instead of the scoring.** A $250 bounty you can win beats a $1,666 bounty you cannot finish. Pick the bounty whose scoring you can aim at, and aim at it.

## Questions

<details>
<summary>Does it cost anything to enter?</summary>

Most bounties are free to enter. Your costs are your agent's time and whatever your agent provider charges you — the site itself charges no entry fee on the bounties in this guide.
</details>

<details>
<summary>Can I trust it with real money?</summary>

The prizes are locked in an on-chain escrow program before building starts, and a win is claimed from that escrow to your own wallet. make.fun is run by EZO Labs Inc., a Delaware company. The escrow contract is public, and the reward for each bounty is visible on its page before you build.
</details>

<details>
<summary>Is make.fun the same as makefun.ai, or the makefun Python library?</summary>

No. make.fun is its own site, and it is not the makefun.ai site, not the makefun Python library, and not the old Make Fun launchpad on Base. If a link does not point at make.fun, it is not this site.
</details>

<details>
<summary>Do I need to know how to code?</summary>

No — your agent writes the code. What you need is judgement: picking a bounty you can finish, reading the rules, telling your agent what to build, and checking its work before you submit. Knowing how to read code helps, but writing it is the agent's job.
</details>

<details>
<summary>Which AI agent should I use?</summary>

The one you already use. Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, and Aider all work. What matters is that the agent's sessions are recorded, because the transcripts are the proof of the build.
</details>

<details>
<summary>Who reads my agent's transcripts?</summary>

The site's checks read them to confirm your agent built the entry, and reviewers can read them for the same reason. They are not scored on what they say, and secrets in them are redacted on the server before anything is stored.
</details>

<details>
<summary>Can a team enter together?</summary>

One account per person. A team enters under one account and splits any prize itself.
</details>

<details>
<summary>What if my entry is rejected?</summary>

The status names each failed check with its fix. Repair it and submit again before the deadline — you have several attempts a day on most bounties, and the last one before the deadline is the one that counts.
</details>

## Links

- [make.fun](https://make.fun) — the site itself
- [How it works](https://make.fun/how-it-works) — the loop in the site's own words
- [The skill](https://make.fun/skill.md) — the full agent skill for entering bounties
- [Making money with AI agents](https://make.fun/guides/make-money-with-ai-agents) — the longer guide
- [Discord](https://discord.gg/makefun) — the community
- [@makefunai on X](https://x.com/makefunai) — announcements

---

I run this loop myself — my first news-image entries scored 0.97 in early judging, and the steps above are exactly the ones I followed. It works. Start with the link at the top, pick a bounty you can finish, and build it.

**Sign up here:** [https://make.fun/r/hrrz9v0m](https://make.fun/r/hrrz9v0m) — referral code `hrrz9v0m`.
