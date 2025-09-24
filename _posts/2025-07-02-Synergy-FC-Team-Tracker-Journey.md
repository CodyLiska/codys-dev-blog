---
layout: post
title: "Building the Synergy FC Team Tracker: My Journey from Idea to App"
date: 2024-07-02 10:00:00 -0700
categories: [react, web-dev, deployment]
excerpt_separator: <!--more-->
---

I wanted to give our coachesa better way to track player development. Google Sheets had gotten us pretty far, but once multiple coaches, skills, and weekly ratings entered the picture, it started to feel like juggling flaming soccer balls.

<!--more-->

# Building the Synergy FC Team Tracker: My Journey from Idea to App

When I first set out to build the **Synergy FC Team Tracker**, I had one
simple goal: give our coaches (myself included) a better way to track
player development. Google Sheets had gotten us pretty far, but once
multiple coaches, skills, and weekly ratings entered the picture, it
started to feel like juggling flaming soccer balls. It was time for a
real app.

### Step 1: The Big Idea

The vision was clear:\
- A web app where each coach could log in\
- Players tied to the right coach\
- Ratings broken down into categories like *psychological, physical,
social-emotional, and technical*\
- Charts and dashboards to make sense of the data

I decided on a **Vue 3 frontend** and a **Node.js/MongoDB backend** ---
mostly because that stack felt light, flexible, and something I could
iterate on fast in my home lab.

### Step 2: Early Wins and Growing Pains

At first, things moved quickly. I set up player creation forms, coach
dashboards, and even pulled in team stats. But then the "little" details
hit me hard:

-   **CORS errors** after I renamed `/backend` to `/api` (rookie move,
    but a good reminder of how tightly frontend and backend need to stay
    in sync).\
-   Struggles with **form state**, like resetting checkboxes or clearing
    update forms after saving. Small things, but they matter a lot for
    usability.\
-   **Pagination** on eligibility calls. I had never tackled pagination
    in C# services before, so it was a steep but worthwhile climb.

### Step 3: Multi-Coach Madness

The biggest challenge? **Multi-coach access.**

At first, I tied access control to player IDs through a `TEAM_MAP`. It
worked, but it was clunky. Then I shifted to using **roles and email
addresses** as the main drivers. That was a game-changer:\
- Admins and head coaches could see all players.\
- Assistant coaches only saw their own.\
- We added JWT handling, refresh tokens, and HTTP-only cookies for
secure sessions.

This was the first time I built **role-based access control** from
scratch, and while I pulled out a few hairs, it was one of those moments
where you realize: *oh, this is how real systems handle access.*

### Step 4: Dashboards & Data

Once authentication was stable, I focused on making the coach dashboards
**actually useful**. That meant:\
- Team skill averages, editable when needed.\
- Charts that updated dynamically when player data changed.\
- Grouping traits by category on a single page (instead of scattering
them across multiple).

I even got nerdy with **timestamp formatting issues** and normalization
in spreadsheets before moving that logic fully into the app. Every bug
taught me a little more about **data consistency**.

### Step 5: Lessons Learned

Looking back, a few lessons stand out:

-   **Don't underestimate "small" UX details.** Resetting a checkbox or
    keeping timestamps consistent sounds minor, but it can make or break
    the experience.\
-   **Role-based access is worth doing right.** Switching from hardcoded
    ID maps to a role-based system was tough, but it unlocked real
    scalability.\
-   **Iteration beats perfection.** I didn't get everything right the
    first time (or the second), but each pass made the app better.\
-   **Have fun with it.** Yes, there were moments I wanted to punt my
    laptop like a soccer ball, but seeing data flow across dashboards
    made it all worth it.

### Step 6: What's Next?

The Team Tracker is already miles ahead of where we started. Coaches can
log in, see their players, and get meaningful insights in seconds. But
the roadmap is still wide open --- maybe mobile support, deeper
analytics, or even AI-powered insights on player development (a coach
can dream, right?).

------------------------------------------------------------------------

## Final Thoughts

Building the Synergy FC Team Tracker has been equal parts **software
engineering bootcamp** and **soccer coaching hackathon**. I learned new
tricks in Vue, Node, and MongoDB; fought my way through auth flows; and
came out the other side with an app that actually helps my team.

It wasn't always smooth, but then again, neither is soccer. Sometimes
you trip, sometimes you score, but the key is to keep playing. And for
me, this project has been one of the most rewarding games yet.
