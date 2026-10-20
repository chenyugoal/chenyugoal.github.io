---
layout: post
title: Today, I stopped building grounded-apply
image: /assets/img/blog/grounded-apply-vision.png
accent_image:
  background: url('/assets/img/blog/jj-ying.jpg') center/cover
  overlay: false
accent_color: '#ccc'
theme_color: '#ccc'
description: >
  https://github.com/chenyugoal/grounded-apply
invert_sidebar: true
---

I built an AI assistant to save time applying for jobs. Naturally, I gave myself another job first.

Today, I’m sharing **grounded-apply**: an incomplete, experimental open-source job-search assistant operated through Codex. It turns approved career facts into reusable memory, helps users discover and compare jobs, and prepares evidence-backed resumes and application answers. I’m also wrapping up its broader development.

As I approach the end of my PhD, I’ve been spending time finding openings, assessing fit, and entering the same information into application forms. I’ve never enjoyed repetitive work.

The idea was a personal assistant that would gradually learn about my experience, find suitable roles, prepare truthful applications, and help fill out forms—with my approval required before remembering new facts about me or submitting anything. At the time (early August 2026), my $200 subscription felt almost unlimited. Building it seemed like a reasonable shortcut.

The first prototype came together quickly. Making it consistently useful was much harder. Performance issues, missing information, and awkward workflows all needed attention. I kept switching between developer and test user: start an application, discover friction, refine the workflow, repeat. The coding agent accelerated implementation. Discovering what actually saved me effort remained my job.

Meanwhile, the assumptions behind the project kept shifting. OpenAI’s announced change to API-dollar-equivalent Pro usage in Codex made me revisit the economics. Meta launched Muse, and I saw people sharing job-application workflows using a general-purpose agent. Before I had a good answer to “Does this save me time?” I was already revisiting the question “Should I still be building it?”

So I’m sharing the working foundation and leaving the larger vision as a wish list. The alpha supports approved career memory, job discovery, and evidence-backed application materials. Browser form filling is unfinished, and final submission stays with the user. I’m not claiming any time savings yet.

My takeaway: AI can shorten the time it takes to build software. It can also shorten the window in which custom software is worth building. Measure the useful outcome early. A convincing demo can arrive quickly; a dependable workflow still takes iteration. And while you work on it, model capabilities, subscription economics, and platform features keep changing.

Move fast, break things, and look ahead. For now, back to the job applications.
