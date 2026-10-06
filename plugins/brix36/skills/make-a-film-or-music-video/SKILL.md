---
name: make-a-film-or-music-video
description: Make a film or music video in the connected Brix36 account. Show the price and wait for one approval before anything is charged.
---

# Make a film or music video

Use the connected Brix36 account. Generation runs on that account's credits. Show the price and wait for one explicit yes before you charge anything.

1. Ask whether this is a Film or a Music video if the customer has not said. `studio_video_start` refuses an absent or unknown kind before it reads the roster.
2. Call `studio_artists_list`. Use an existing artist name when they pick one. For a new fictional character, pass that name to `studio_video_start` with `createArtist` true, or call `studio_artist_create` for a `fictional_character`. Do not create a real person. A real person uses the Brix36 app consent flow.
3. For a film, call `studio_film_script_write`. For a music video, the start call needs `songTitle`. Use `studio_song_attach` when the song is already on the account.
4. Call `studio_video_start` with an explicit kind, `Film` or `Music video`, the artist name, and `durationMs`, using the length the customer asked for.
5. Call `studio_generation_quote`. Show the exact price in the chat. Do not confirm yet.
6. Wait for one explicit yes.
7. Call `studio_generation_confirm` once for that quote. Do not confirm again unless they ask for a new change and you have shown a new quote.
8. Call `studio_generation_status` until it returns a video link, then `studio_video_preview` to play it. Use `studio_video_status` if you need the saved project state.
9. If the balance is short, repeat the credit information the tool returns and stop. Do not open a checkout and do not confirm.

Use the customer's own material, a fictional character, or a person who has given permission.
