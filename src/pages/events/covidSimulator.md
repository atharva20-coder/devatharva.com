---
title: Corona Simulator 🦠
slug: simulator
date: 2020-11-3
author: Atharva Joshi
read_time: 1
tags: ["HTML", "CSS", "JS"]
order: 2
draft: true
past: false
emoji: "📈"
---

Calling all backend and frontend developers to participate in the October Hackathon!

## 🎯 Objective

As a developer advocate at Agora, I am always looking to collaborate with Advocates from other companies. Wouldn't it be nice to have a website I can visit to find other advocates?

In this hackathon we are gonna work together as backend and frontend developers to fix this issue.

Pick one of the two challenges below and build based off of the parameters set.

## 📆 Important Dates

- Start date: 10/10
- Submission deadline: 11/5
- Winners announcement: Maybe 11/10??

## 💰 Prize Money

6 Grand prize winners for a total of $1,500!

✋ How to participate

- Register - <a href="https://codebattles.dev/" target="_blanl">CodeBattles.dev</a>
- Pick a challange
- Submit project before deadline

<br>

### ⚙️ Challenge 1 - 💻 For Backend Devs

<br>

💰 Prize money: $200 - 5 winners will be selected

Build an API that outputs a list of developer advocates with their details such as where they work, social links, bio, etc. Example API response bellow.

**Project Requirements**

Your API should at a minumum have these 2 endpoints

1. `/advocates`
2. `/advocates/:username`

Your API should be searchable (By user name), paginated.

Ex:

`/advocates/?query=dennis`

Your endpoints should provide links to user profile pictures and company logos.

User Data Ex:

```json
// advocates/:id
{
  "advocates": [
    {
      "profile_pic": "https://pbs.twimg.com/profile_images/1489066537407365126/iViPGBVE_400x400.jpg",
      "username": "dennisivy11",
      "name": "Dennis Ivy",
      "bio": "YouTuber, contributor at @traversymedia , developer advocate @agoraio and online instructor.",
      "twitter": "https://twitter.com/dennisivy11"
    }
  ]
}
```

**Submission Requirements**

- Github link
- Live URL - API must be hosted
- Tag Agora on Twitter OR Linkedin

🧑‍⚖️ What Judges Are Looking For

Judges are looking for an API that works and has data as in example above. If requirements are met, your name will be entered into a raffle for a chance to win $200. 5 winners will be chosen.

<br>

### ⚙️ Challenge 2 - 🎨 For Frontend Devs & Designers

<br>

💰 Prize money: $500 - 1 winner will be selected

Using the the data provided in this link (<a href="https://cados.up.railway.app/" target="_blank">cados.up.railway.app</a>), design and code up a template which consumes the API.

Your website should at a minumum have these 2 pages

1. `/advocates`
2. `/advocates/:username`

`Requirements`

- Github link
- Live URL
- 2 Pages

🧑‍⚖️ What Judges Are Looking For

Judges are looking for the BEST design and most usable template (clean code). The winning template will be used in a live project to complete the website "cados.dev".

### Links 🔗

<div style="display: flex; flex-wrap: wrap; gap: 10px;">

<div style="flex: 1; min-width: 150px; border: 1px solid #ddd; border-radius: 5px; padding: 10px; text-align: center;">
  <a href="https://github.com/atharva20-coder/covid-simulation" target="_blank" style="display: flex; align-items: center; justify-content: center;">
    <svg height="24" width="24" viewBox="0 0 16 16" version="1.1" aria-hidden="true" style="fill: #000; margin-right: 5px;">
      <path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.45.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
    GitHub Repository
  </a>
</div>

<div style="flex: 1; min-width: 150px; border: 1px solid #ddd; border-radius: 5px; padding: 10px; text-align: center;">
  <a href="https://covid-india-simulation.netlify.app/" target="_blank">Live Preview</a>
</div>
</div>

<br>
