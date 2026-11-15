# Stories by Himadri

## 1. Add his real photos
- Put images in `photos/` (JPG, about 1600px on the long side, under 400 KB each).
- In `site.json`, edit the `gallery` list: set `src` (e.g. "photos/wedding-01.jpg"), `caption`, `cat` (one of `categories`) and `w`/`h` (pixel size).
- Also set `heroImage` and `about.image`.
- The `photos/01.svg … 09.svg` files are sample artwork. Delete them once real photos are in.

## 1b. Or show his Instagram posts directly
In `site.json`, add post links to `instagramPosts`, e.g. `["https://www.instagram.com/p/XXXXXXXX/"]`. A "From Instagram" section then appears, with his real photos and no downloading.

## 2. Edit details
`site.json`: `whatsapp` (country code + number, no + or spaces), text, packages and prices, testimonials, FAQ.

## 3. Update availability (`availability.json`)
```json
{ "updated": "2026-11-15",
  "slots": {
    "2026-11-22": ["Morning (7–11 am)", "Evening (4–7 pm)"],
    "2026-11-23": []
  } }
```
Date with slots = open. `[]` = shown as booked. Date missing = unavailable. Edit on github.com and commit; Vercel redeploys in ~30 s.

## 4. Deploy
Push to GitHub → vercel.com → Add New → Project → import repo → Deploy. No build settings.

## Notes
- On Vercel the page always reads the latest `site.json` and `availability.json`. A copy is also built into `index.html` so the page still shows content when you open the file directly from your computer.
- The "Follow along" section embeds his Instagram profile. If Instagram refuses to show it in your browser, the "Open Instagram" button still works. For a full auto-updating photo grid, a free widget such as Behold.so or Elfsight can be pasted in its place.
- Photos named 01–18 in `photos/` are sample artwork. Replace them with his real photos.

## Videos
Edit `videos` in `site.json`. Each entry has a `title` and a `type`:
- YouTube: `{"title":"Wedding highlights","type":"youtube","url":"https://www.youtube.com/watch?v=XXXXXXXXXXX"}`
- Instagram reel: `{"title":"Reel","type":"instagram","url":"https://www.instagram.com/reel/XXXX/","ratio":"9/16"}`
- Facebook video: `{"title":"Film","type":"facebook","url":"https://www.facebook.com/.../videos/123/"}`
- Your own file: put an MP4 (H.264, under 25 MB) in `videos/`: `{"title":"Teaser","type":"file","src":"videos/teaser.mp4","poster":"videos/teaser.jpg"}`
Best option for long wedding films: upload to YouTube (unlisted is fine) and paste the link. Delete the sample entry when you add real ones. Remove all entries to hide the section.
