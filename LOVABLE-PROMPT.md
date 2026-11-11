# Prompt for Lovable

Copy everything between the lines below and paste it into Lovable.

---

Add a new page to my site at /scoreboard called "Leadership Notes Boost Scoreboard", and add "Scoreboard" to the main navigation.

Build the page from this HTML file, keeping its layout, colors, fonts and text exactly as they are:
https://raw.githubusercontent.com/billm84-png/notes-boost-scoreboard/main/scoreboard.html

Important rules for this page:
1. Do not hard-code any of the numbers, names or leaderboard rows. Every number and every leaderboard entry must come from this public data file, fetched in the visitor's browser each time the page loads:
   https://raw.githubusercontent.com/billm84-png/notes-boost-scoreboard/main/scoreboard.json
2. The data file is refreshed the day after every boost. When it changes, the page must show the new numbers on the next visit with no change to the site, so do not copy the JSON into the project and do not cache it at build time. Add a cache-busting query string (for example ?t= plus the current time) when fetching it.
3. The page needs no login, no database and no API keys. The data file is public.
4. Map the JSON like this:
   - latest_boost.label: the boost date in the intro line
   - room.subscribers, room.followers, room.writers, room.writers_showed_up, room.first_timers, room.member_replies_per_note (one decimal), room.median_subscribers: the "What we add up to" cards
   - leaderboards.most_generous, leaderboards.best_conversation, leaderboards.welcome_crew: the three leaderboard cards. Each row has rank, name, value and url. Show rank, the name as a link to url (opens in a new tab) and value. Rank 1 gets the gold circle.
   - leaderboards.on_a_streak: the "On a Streak" card, one pill per name, each linking to url
   - playbook.early_replies, playbook.late_replies, playbook.text_only_replies, playbook.with_image_replies (one decimal): the numbers inside playbook tips 1 and 2
5. If the data file can't be loaded, show a short friendly message instead of empty boxes.
6. Keep it readable on a phone.

---
