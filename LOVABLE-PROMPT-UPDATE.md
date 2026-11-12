# Prompt for Lovable: scoreboard update (weekly boards, room reach, growth, streak badges)

Copy everything between the lines below and paste it into Lovable as one message. It updates the existing /scoreboard page. Until you run it, the current page keeps working as it is.

---

Update the existing /scoreboard page. Keep its layout, colors, fonts and the fetch rules exactly as they are now: every number still comes from https://raw.githubusercontent.com/billm84-png/notes-boost-scoreboard/main/scoreboard.json, fetched in the visitor's browser on every load with a ?t= plus current time cache-buster, never copied into the project and never cached at build time. Nothing is hard-coded.

Make these five changes.

1. Leaderboards become weekly.
   - Retitle the leaderboard section "This week's standouts" and show week.label under the title (for example "Week of Nov 9").
   - Fill the three boards from leaderboards_week.most_generous, leaderboards_week.best_conversation and leaderboards_week.welcome_crew. Each row has rank, name, value and url. Link each name to its url.
   - If week.read is "early", add a small note under the title: "Early read. Final numbers on Friday."
   - Keep the per-boost boards (leaderboards.*) available under a collapsed "Latest boost" toggle, labeled with latest_boost.label.

2. "What we add up to" cards cover the whole room.
   - Subscribers card: room_reach.subscribers. Followers card: room_reach.followers.
   - Under the cards, one line: "Combined reach of the {room_reach.members_counted} of our {room_reach.room_members} members we can count, coaches included."
   - Keep the turnout cards but read them from this_week and say "this week": this_week.writers_showed_up ("writers showed up this week"), this_week.first_timers ("first-timers this week"), this_week.member_replies_per_note with one decimal ("member replies per Note this week").

3. New section: "How we're growing", placed after the reach cards.
   - Subscribers: growth.subscribers.change, shown with a plus sign when positive, then "since {growth.since}" (format the date as "Nov 12").
   - Two smaller numbers under it: growth.subscribers.from_members_growing ("from members growing") and growth.subscribers.from_new_members ("from new members").
   - The same three numbers for followers from growth.followers.
   - When growth.subscribers.change and growth.followers.change are both 0, show this instead of the numbers: "Our first count was {growth.since}. Growth shows here from the next boost."

4. Streak badges.
   - Add a "Streaks" section listing every entry in members (name linked to url) with a badge from current_streak: Gold at 24 or more, Silver at 12 or more, Bronze at 4 or more. Members under 4 get no badge.
   - Sort by current_streak, highest first, then by name. Show only members with a badge; when nobody has one yet, show: "Badges start at a 4-boost streak. Keep dropping."

5. Keep everything else on the page (intro line, playbook, history) exactly as it is.

Do not add a login, a database or API keys. The data file is public.

---
