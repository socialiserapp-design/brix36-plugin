---
name: find-play-and-download-your-videos
description: Find, play, rename and download the finished Brix36 videos already in the connected account. Use it when someone asks to see, watch, rename, sort by artist or download their existing Brix36 videos.
---

# Your finished Brix36 videos

This works only with finished videos that are already in the connected Brix36 account. It never makes a new video and never spends credits.

1. To find videos, call `studio_projects_list`. It lists finished videos newest first. To narrow by artist, call `studio_artists_list` (with `query` for part of a name), then pass that `artistId` to `studio_projects_list`. Use `cursor` to page.
2. To watch one, call `studio_video_preview` with its `projectId` and share the playback link it returns.
3. To download one, call `studio_video_export` with its `projectId`. Share the download link and say it is temporary. Anyone with the link can open it until it expires.
4. To rename one, use the new title the customer already gave. Ask for it only if they have not given one. Then call `studio_project_rename` with the `projectId`, the `expectedRevision` from the latest list, and the new `title` (plus `songTitle` if they want that changed). If the revision is stale, list again and retry once.
5. If someone asks to create a new video, or to change the footage or audio of an existing one, say this connector only works with finished videos and point them to the Brix36 app. Finding, playing, renaming and downloading work as usual.
6. Only if someone asks to open or edit a finished video in Brix36, give the `webUrl` from `studio_projects_list` or `studio_video_preview` as a plain link labelled "Open in Brix36". If they ask to open their whole library, use the list's top-level `webUrl`. Do not offer these links at any other time.
