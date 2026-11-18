# Donner Snow settings

This repository holds **`settings.json`**, the one file that controls the webcams in
both Donner Snow apps: the web page at donnerskiranch.com/snow and the Roku app.

Change it here and both apps pick up the change on their own, usually within
10–30 minutes. Nothing needs to be rebuilt or re-uploaded.

Published at: https://donnerskiranch.github.io/donner-snow-settings/settings.json

> This repository is **public** so the apps can read the file. Only put things here
> that are fine for anyone to see (cam names, YouTube IDs, messages). Never passwords
> or private links.

## Changing a cam (from a browser)

1. Open `settings.json` in this repository on github.com and click the **pencil**
   (Edit) icon.
2. Make the change (see below).
3. Click **Commit changes…**, write a short note such as "New Deck Cam stream ID",
   and commit.

### When a stream restarts and the cam stops working

YouTube gives a restarted stream a new video ID. Open the stream on YouTube and copy
the part after `watch?v=` in its address:

```
https://www.youtube.com/watch?v=ArDIIhAHwWE
                                ^^^^^^^^^^^  this is the youtubeId
```

Paste it between the quotes of that cam's `"youtubeId"`.

### Taking a cam offline, or bringing it back

- **Offline:** empty the ID, `"youtubeId": ""`. The apps show that cam's
  `"offlineMessage"` instead.
- **Back online:** put its YouTube video ID back in `"youtubeId"`.

### Adding a cam

Copy one whole `{ ... }` block, paste it after the last one and put a comma between
the blocks. The apps show cams in the order they appear here.

## Rules that keep the file valid

- Keep the quotes around every value and the commas between items.
- No comma after the last item in a list.
- If you break the file, the apps ignore it and fall back to their built-in cams,
  so nothing goes blank. Fix the file and they pick it up again. github.com shows red marks for some mistakes; you can also
  paste the file into https://jsonlint.com to check it.
- Every change is kept in the history, so any edit can be undone.
