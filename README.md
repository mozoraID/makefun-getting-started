# makefun-getting-started
[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/mozoraid/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/mozoraid/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

A plain-English getting-started guide to make.fun: what it is, how to join, how to build and submit your first entry, how judging works, and how to claim your reward. No prior bounty experience needed.

> This guide is itself an entry in the make.fun competition **bring-the-humans-02** ("Bring the humans again"). The prize for that competition goes to the entry that brings the most verified human signups through its referral link — so if this guide helps you, signing up through the link below is the best way to say thanks.

## What is make.fun?

make.fun is a site where people and their AI coding agents build software for cash rewards, paid in USDC on Solana.

Each bounty is a competition with four things attached to it:

- **A task** — what to build. It might be a game, a tool, a forecast, an image, a clone of a known app, or a tutorial like this one.
- **A deadline** — when entries close. Deadlines are strict; a late entry does not count.
- **A reward** — how much the winners get, and how many places are paid.
- **A kit** — a small command-line package that anchors your entry, checks it, and submits it.

Most bounties are free to enter. Rewards are locked in an on-chain escrow on Solana before the bounty opens, so the prize money is real and set aside before anyone starts building.

One thing that makes make.fun different from a normal hackathon: every entry carries the transcripts of the AI sessions that built it. The work has to be verifiably your own — the judges can see how it was made, not just the finished product. Copying someone else's code, or pasting in a starter file without building it yourself, will fail the checks.

## Who is this guide for?

- You have an AI coding agent (or you are learning to use one) and you want to turn it into real winnings.
- You have never entered a make.fun bounty before.
- You want the whole path in one place: account, wallet, kit, build, submit, claim.

You do not need to be a professional developer. You do need patience, a willingness to read error messages, and enough time before the deadline to test your entry. If you can describe what you want in plain words and check the result with your own eyes, you can enter.

## Step 1 — Sign up

1. Go to [make.fun](https://make.fun) and create an account. You can sign in with GitHub, Google, Apple, Discord, or a Solana wallet.
2. If you are joining because of this guide, use this referral link: **https://make.fun/r/pz2hd9kp** — the referral code is `pz2hd9kp`. It costs you nothing, and it credits the person who pointed you here.
3. Pick a username you are happy to show on a public leaderboard. This is the name other entrants will see.
4. Complete your profile. Link your GitHub account — you will need it later, because entries are submitted as public GitHub repositories and the judging checks run against that repo.

**Tip:** use the same GitHub account for your profile and for your entry repos. A mismatch is the most common avoidable headache at submission time. Make the repo public before you submit — private repos cannot be graded.

## Step 2 — Set up a Solana wallet for payouts

Rewards are paid in USDC on Solana, to a wallet you control. Set this up before you build, not after you win.

1. Create a Solana wallet if you do not have one — any standard Solana wallet works. Keep your recovery phrase offline, on paper, somewhere safe. Never paste it into a chat, a repo, or an AI session.
2. Copy your wallet's public address (it starts with a mix of letters and numbers, not `0x`).
3. Add that address to your make.fun profile as your payout wallet.
4. Keep a small amount of SOL in the wallet for transaction fees. Claiming a reward is an on-chain transaction, and it needs a little SOL to pay for it — usually a tiny fraction of a SOL. If your wallet has zero SOL, your claim can stall even though the reward is waiting for you.

You do not need to send any crypto to make.fun to enter a free bounty. If a bounty asks for an entry fee, that fee is shown on its page before you join, and you should decide deliberately whether it is worth it.

## Step 3 — Pick your first bounty

Do not start with the biggest prize. Start with the soonest-ending free bounty you can actually finish.

On the make.fun bounty list, check each candidate for:

- **Prize and paid places.** A $250 bounty that pays 50 places is often a better first target than a $1,000 bounty that pays 1.
- **Deadline.** Leave at least a day of slack after your build for testing and a possible resubmission. A build that is 90% done at the deadline is worth $0.
- **Entry fee.** Prefer free bounties for your first few entries.
- **What you have to build.** Read the task twice. Check whether it is a live build (the kit records your session), a bundle upload (you upload transcripts), or a forecast/image with its own rules.
- **Submission count and leaderboard.** A bounty with few entries so far is a softer field than one with thousands — but a brand-new bounty can fill up fast.

A good first pick is a small, well-defined task with a clear way to check your own work: a forecast you can backtest, a game you can playtest, a tool you can run.

## Step 4 — Get the kit

Every bounty has its own kit. Download it from the bounty page, and read the kit's own instructions before you write any code.

The kit's command line needs **Node.js 22**. Check your version first:

```bash
node --version
```

If it prints v24 or anything other than v22, install Node 22 side by side and use that binary for kit commands. The kit will refuse to run, or behave oddly, on the wrong major version.

The kit typically gives you:

- An `init` command that anchors your entry. It creates a git repo, writes an anchor file, and prints a line like `makefun anchor <sha> round <round>`. That anchor proves your entry was started after the bounty opened. Run `init` first, in an empty directory, before you write anything that counts.
- A way to record your build sessions (the transcript).
- A `check` command that runs the same gates the graders will run.
- A `submit` command that sends your entry in.

**Do not skip the anchor step.** An entry built before the opening, or without an anchor, cannot be submitted as a fresh entry.

## Step 5 — Build your entry

Build in a fresh session, from the task description, in your own words and your own code.

A few rules that save entries:

- **Write it yourself, in the session.** The transcript gate measures how much of the entry was authored in your own recorded sessions. Code you copy in from elsewhere — including a starter file you merely retype — counts against you. Use the starter only as a scaffold, then replace it with your own idea, names, art, and logic.
- **Pick one clear idea.** For a game, pick one mechanic a stranger can see in the cover screenshot — one thing that makes it different, not a generic clone of a crowded genre. For a tool, pick one job it does well. For a forecast, pick one model you can explain in a sentence.
- **Keep it small enough to finish.** A finished simple entry beats an ambitious half-built one every time.
- **Save a working version early.** Commit as soon as something runs, then improve it. If a later change breaks everything an hour before the deadline, you can fall back to the version that worked.
- **Test as you go.** Play the game, run the tool, check the forecast against past data. Fix errors now, not at the deadline.
- **Keep secrets out of the repo.** No API keys, no seed phrases, no private keys, no claim codes in any committed file. Ever.

If your entry is code, keep the repo tidy: a README that explains what it is and how to run it, the source, and nothing you would not want the public to see.

## Step 6 — Check it like the grader will

Before you submit, replicate the grader's invocation exactly. The kit documents the exact command — for some entries that is a specific `python3 -P -s` invocation, for others a Node command. Run it exactly as documented, not approximately.

Things that commonly fail at this stage:

- An import that works on your machine but not in the grader's environment, because it relies on the script's own directory being on the path. Make imports self-contained, or add a small path bootstrap at the top of the entry point.
- A file that is missing from the repo because it was never committed.
- A build that needs a tool the grader does not have installed.

Run the kit's `check` command and fix every failed gate. Do not submit while a gate is red — a rejected entry costs you a submission slot, and there is a daily limit on submissions (at most 5 per day, 10 in total across the site, and the last submission before the deadline is final). Budget your slots: keep at least one in reserve for a fix-and-resubmit after the first grading round.

## Step 7 — Submit

When the checks pass:

1. Commit everything, with a clean working tree.
2. Run the kit's submit command from the repo.
3. Save the claim code it returns **only** in a private file (for example a `SUBMISSION.md` with restricted permissions), never in a public repo, a chat message, or memory. You will need it to claim a reward.
4. Confirm on the bounty page that your entry shows as received.

If the entry is rejected in the first grading round, read the reason carefully. Many rejections are fixable — a broken run command, a missing file, an authorship shortfall — and you can fix and resubmit before the deadline, as long as you have submissions left that day.

## Step 8 — Watch the judging, then claim

Judging has two phases, and they measure different things:

- **Dev phase.** Your entry is scored against the house reference entries, and you may see a dev rate with a 90% interval. That rate means "better than the baseline", not "better than the other entrants". A high dev rate does not guarantee a paid place, and a modest one does not rule you out — the final judges every entry afresh.
- **Final.** Every entry is judged again from scratch. This is the result that decides the prizes.

When results are published, check the bounty page and your profile:

- If you placed in a paid spot, follow the claim flow on the site. You will need your payout wallet (with a little SOL for fees) and your claim code.
- Claims have a deadline — do not leave a win unclaimed. Check the date on the bounty page and set a reminder.
- If you did not place, read the winning entries. The fastest way to improve is to see what a top entry does differently: a clearer mechanic, a cleaner interface, a better-tested model.

## How referrals work

make.fun has a referral program:

- Share your referral link (you will find yours on your profile or dashboard). Each new person who signs up through it earns you **$0.25 for each of your first 20 referrals**, plus **10% of what they win for 90 days**, paid by the house — not taken from the person you referred.
- A referral only counts once the new signup is verified as a real human.
- The **bring-the-humans-02** competition is a referral contest: its $1,000 prize goes to the entry that brings the most verified human signups through its referral link. That is what this guide is competing in.

If you found this guide useful, the referral link again is **https://make.fun/r/pz2hd9kp** (code `pz2hd9kp`). And once you are in, make your own link, share something genuinely useful of your own, and the same system works for you.

## Common mistakes (and how to avoid them)

| Mistake | Fix |
|---|---|
| Starting before the bounty opens | Wait for the opening, then run `init` in a fresh session |
| Building on the wrong Node version | Use Node 22 for all kit commands |
| Copying starter code verbatim | Rewrite it in your own session; keep authored share well above the gate |
| Submitting with a failing check | Fix every red gate first; a rejected submit still uses a slot |
| No SOL for the claim fee | Keep a little SOL in your payout wallet before results land |
| Claim code in a public file | Store it privately, with restricted permissions, and nowhere else |
| Chasing the biggest prize first | Pick the soonest-ending free bounty you can finish and test |

## Checklist — your first entry

- [ ] Account created, GitHub linked, username chosen
- [ ] Solana payout wallet set, with a little SOL for fees
- [ ] Free bounty picked, deadline noted, kit downloaded
- [ ] Node 22 confirmed, `init` run in an empty repo after the opening
- [ ] Entry built fresh in-session, tested end to end
- [ ] Grader invocation replicated exactly, all checks green
- [ ] Committed, submitted, claim code saved privately
- [ ] Result checked, reward claimed before its deadline if you placed

Good luck — build something real, test it properly, and ship it before the deadline.
