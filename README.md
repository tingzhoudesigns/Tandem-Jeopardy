[README.md](https://github.com/user-attachments/files/30213977/README.md)
# Tandem Jeopardy

A browser-based, Jeopardy-style team trivia game built to engage onsite and remote players on equal footing during a hybrid event. One HTML file, no dependencies, no login, no internet required once loaded. It runs anywhere a browser does.

**[▶ Play it live](https://tingzhoudesigns.github.io/Tandem-Jeopardy/)** · **[More work](https://tingzhoudesigns.com)**


---

## What this is

A facilitator-run trivia game for 3 to 5 teams. Five categories, twenty-five questions of escalating difficulty, and a live scoreboard that everyone can see whether they are in the room or on a video call. Teams take turns choosing a question from the board, answer it, and either win the points or score zero. When the board is cleared, the game ranks the teams.

It borrows the familiar Jeopardy board layout but changes the mechanic: instead of buzzer-and-response, every question is multiple choice, multiple answer, or true/false, and each one reveals the correct answer before play continues.

## The problem it solves

Hybrid events are hard to run well. The usual engagement tools (live polls, Kahoot, group chat) quietly assume everyone shares one context. In a mixed room, the people physically present dominate the energy, and remote participants end up watching rather than playing.

This game was built so that a remote team and an onsite team are structurally identical. Everyone sees the same board on their own screen, teams take turns in a fixed rotation, and the running scores are visible to all. No one needs to be in the room to compete, and no one is disadvantaged by joining from home.

## How it works

- **Team setup:** choose 3, 4, or 5 teams and give each a name. Names carry through to the scoreboard and the final standings.
- **Turn rotation:** teams pick in order. With 3 or 4 teams the questions do not divide evenly, so the first team gets one extra pick. Assigning that first slot to an all-remote team is a deliberate way to offset the airtime imbalance of a hybrid room. With 5 teams the twenty-five questions split evenly and every team gets exactly five picks.
- **Question types:** multiple choice (one answer), multiple answer (select every correct option), and true/false. Multiple-answer questions are scored all or nothing: the exact full set earns the points, anything less scores zero.
- **Answer reveal:** every question shows the correct answer after it is answered, right or wrong, so play doubles as a learning moment rather than only a competition.
- **The board as a record:** answered cards flip and gray out, showing which team took each question and whether they scored. A cleared board reads as a history of the game.
- **Final standings:** teams are ranked by score, with tied teams sharing a rank.

## Design decisions

The mechanics are simple on purpose. The thinking underneath them is where the instructional-design work lives.

- **Equal footing was the whole point.** The format was chosen because it removes the hybrid disadvantage rather than working around it. That constraint drove the design more than any aesthetic choice did.
- **The turn-order privilege is inclusion, not just math.** The uneven split at 3 and 4 teams could have been a nuisance. Instead it became a feature: the structurally advantaged first pick goes to the group that a hybrid room usually shortchanges.
- **Difficulty escalates by point value.** The 200-point questions build early confidence and shared footing; the 1000-point questions reward genuine depth. This mirrors how a well-sequenced assessment ramps rather than front-loading its hardest items.
- **Answer reveal makes it formative.** Because the content is company and diabetes knowledge, surfacing the correct answer after every question reinforces the material for everyone at the table, which is the actual goal of a knowledge-building icebreaker.
- **Scoring stays unambiguous for live play.** All-or-nothing multiple-answer scoring avoids partial-credit arguments in a fast, facilitator-run setting. A small number of open-response questions are handled with a facilitator judgment call built into the answer options, keeping the flow moving without a text-matching engine to misfire.

## Running and editing it

**To run:** open the HTML file in any modern browser, or host it on GitHub Pages. No build step, no server, no account.

**Refresh recovery:** the game saves its state to the browser after every question, so an accidental refresh mid-session restores the board, scores, and turn order exactly where they were. (This relies on browser storage and works in the deployed or downloaded file.)

**To edit the questions:** all twenty-five questions live in a single, commented data block at the top of the file. Each question is one object with its category, point value, type, text, options, and the index positions of the correct answers. The comment banner explains the format. If you change questions after a game has been played and saved in a browser, increment the `DATA_VERSION` constant so any stale saved game is discarded rather than resumed against the new content.

## Built with an AI-assisted workflow

This was produced with a spec-driven, human-in-charge process. The questions, the mechanics, the design requirements, and the code edits were mine; an AI assistant drafted the implementation from that specification, and I reviewed, corrected, and deployed it. The point is not that AI made a game. It is that disciplined, well-specified AI use collapses production time while the design expertise stays with the designer. A comparable build in a traditional authoring tool takes hours to days; this took a fraction of that, without giving up control of a single design decision.

## Credits

Designed and built by **Ting Zhou**, instructional designer.
Portfolio: [tingzhoudesigns.com](https://tingzhoudesigns.com) · LinkedIn: [ting-zhou-designs](https://www.linkedin.com/in/ting-zhou-designs)

Fork it and adapt it for your own team events.
