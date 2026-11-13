# Prompt for Lovable: scoreboard update (earned badges, new members, room reach, growth)

Copy everything between the lines below and paste it into Lovable as one message. It updates the existing /scoreboard page and replaces the earlier update prompt. Until you run it, the current page keeps working as it is.

---

Update the existing /scoreboard page. Keep its layout, colors (navy #0F2A58, gold #C9952B), fonts (EB Garamond headings, Plus Jakarta Sans text) and fetch rules exactly as they are now: every number and name still comes from https://raw.githubusercontent.com/billm84-png/notes-boost-scoreboard/main/scoreboard.json, fetched in the visitor's browser on every load with a ?t= plus current time cache-buster, never copied into the project and never cached at build time. Nothing is hard-coded.

Make these four changes.

1. Replace the ranked leaderboards with earned badges.
   - Remove the ranked Most Generous, Best Conversation and Welcome Crew boards (rank numbers, 1st/2nd/3rd styling). Nobody is ranked against anyone else on this page.
   - Add a section titled "This week's badges" with badges_week.label under the title (for example "Week of Nov 9"). If badges_week.read is "early", add a small note: "Thursday is an early read. Final numbers on Friday."
   - Under the title, a short legend with one line per badge, using the text in badges_week.rules:
     - Most Generous (gold badge): rules.most_generous
     - Generous (navy badge): rules.generous
     - Welcome Crew (green badge): rules.welcome_crew
     - Streak badges, Bronze, Silver and Gold: rules.streak_bronze, rules.streak_silver, rules.streak_gold
   - Then a list, one row per entry in badges_week.members, in the order given: the member's name on the left, linked to url, and the badges they earned on the right as small pill-shaped badges with an icon. The badge codes in each entry's badges array are most_generous, generous, welcome_crew, streak_bronze, streak_silver and streak_gold.
   - Above the list, a one-line summary from badges_week.counts, for example "12 Most Generous, 12 Generous, 22 Welcome Crew this week." Leave out any badge whose count is 0.
   - Do not show the numbers behind the badges (best_boost_comments, first_timers_welcomed). The badge is the recognition.
   - If badges_week.members is empty, show: "Badges are earned at every boost. Drop a Note, comment on 5 or more, and welcome the first-timers."

2. New section: "Welcome to the room", placed after the badges.
   - One line: "First boost this week:" followed by every name in new_members_week.members, each linked to its url, separated by commas.
   - If the list is empty, hide the section.

3. "What we add up to" cards cover the whole room.
   - Subscribers card: room_reach.subscribers. Followers card: room_reach.followers.
   - Under the cards, one line: "Combined reach of the {room_reach.members_counted} of our {room_reach.room_members} members we can count, coaches included."
   - Read the turnout cards from this_week and say "this week": this_week.writers_showed_up ("writers showed up this week"), this_week.first_timers ("first-timers this week"), this_week.member_replies_per_note with one decimal ("member replies per Note this week").

4. New section: "How we're growing", placed after the reach cards.
   - Subscribers: growth.subscribers.change, with a plus sign when positive, then "since {growth.since}" (format the date as "Nov 12").
   - Two smaller numbers under it: growth.subscribers.from_members_growing ("from members growing") and growth.subscribers.from_new_members ("from new members").
   - The same three numbers for followers from growth.followers.
   - When growth.subscribers.change and growth.followers.change are both 0, show this instead: "Our first count was {growth.since}. Growth shows here from the next boost."

Keep everything else on the page (intro line, playbook, history) as it is. Do not add a login, a database or API keys. The data file is public.

---
