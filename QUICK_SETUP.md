# Quick Setup Checklist

## Before You Upload to GitHub

- [ ] Get your three Vimeo video IDs
- [ ] Decide on a password for the course
- [ ] Have your logo image ready (optional)

## Changes to Make in video-course.html

### 1. Set Password (Line 476)
```javascript
const COURSE_PASSWORD = "your_password_here"; // Replace with your password
```

### 2. Add Video IDs (Lines 394, 407, 420)

**Video 1 (Line 394):**
```html
<iframe src="https://player.vimeo.com/video/YOUR_VIMEO_VIDEO_ID_1"
```
Replace `YOUR_VIMEO_VIDEO_ID_1` with your actual ID

**Video 2 (Line 407):**
```html
<iframe src="https://player.vimeo.com/video/YOUR_VIMEO_VIDEO_ID_2"
```
Replace `YOUR_VIMEO_VIDEO_ID_2` with your actual ID

**Video 3 (Line 420):**
```html
<iframe src="https://player.vimeo.com/video/YOUR_VIMEO_VIDEO_ID_3"
```
Replace `YOUR_VIMEO_VIDEO_ID_3` with your actual ID

### 3. Test It!
- [ ] Open the HTML file in a browser
- [ ] Enter your password
- [ ] Check that all videos load
- [ ] Watch at least 90% of each video
- [ ] Verify certificate appears
- [ ] Enter your name and generate certificate
- [ ] Download PDF and check it looks good

## To Add to WordPress

1. Copy the ENTIRE contents of `video-course.html`
2. In Elementor, add an "HTML" widget
3. Paste the code
4. Save and preview

## Quick Vimeo Settings Check

For each video in Vimeo:
- Go to Video Settings → Privacy
- Set to "Public" or "Unlisted" (not "Private")
- Go to Embed → Enable "Show embedded videos on [your domain]"
- Enable "Playback controls"

## Testing Checklist

- [ ] Password overlay appears on page load
- [ ] Can enter password and access videos
- [ ] All three videos are visible
- [ ] Videos play when clicked
- [ ] Progress bars update as video plays
- [ ] Each video shows "✓ Completed" at 90%
- [ ] Certificate section appears after all videos complete
- [ ] Can enter name in certificate
- [ ] Certificate preview displays correctly
- [ ] PDF downloads with correct name and date

## Common Issues

**Videos won't play:**
→ Check Vimeo privacy settings and video IDs

**Password doesn't work:**
→ Check spelling and case (it's case-sensitive!)

**Certificate doesn't appear:**
→ Make sure you watch 90% of ALL THREE videos

**PDF won't download:**
→ Check browser permissions for downloads

---

That's it! Once everything works, commit to GitHub and deploy to your WordPress site.