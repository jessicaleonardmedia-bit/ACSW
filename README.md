# Social Work and Neurodiversity Video Course

A clean, professional video course platform with password protection, progress tracking, and automatic certificate generation.

## Features

- ✅ Password-protected course access
- ✅ Three-video grid layout with hover effects
- ✅ Real-time progress tracking (90% completion threshold)
- ✅ Automatic certificate generation
- ✅ Downloadable PDF certificates
- ✅ Responsive design for mobile and desktop
- ✅ Montserrat font throughout
- ✅ Custom color scheme (magenta, purple, yellow, sage)

## Setup Instructions

### 1. Get Your Vimeo Video IDs

For each video you want to embed:
1. Go to your video on Vimeo
2. Look at the URL: `https://vimeo.com/123456789`
3. The number at the end (e.g., `123456789`) is your video ID

### 2. Update the HTML File

Open `video-course.html` and make these changes:

#### A. Set Your Password (Line 476)
```javascript
const COURSE_PASSWORD = "your_password_here"; // CHANGE THIS
```
Replace `"your_password_here"` with your desired password.

#### B. Add Your Vimeo Video IDs (Lines 394, 407, 420)

Find these three sections and replace `YOUR_VIMEO_VIDEO_ID_1`, `YOUR_VIMEO_VIDEO_ID_2`, and `YOUR_VIMEO_VIDEO_ID_3` with your actual video IDs:

```html
<!-- Video 1 -->
<iframe src="https://player.vimeo.com/video/YOUR_VIMEO_VIDEO_ID_1" ...>

<!-- Video 2 -->
<iframe src="https://player.vimeo.com/video/YOUR_VIMEO_VIDEO_ID_2" ...>

<!-- Video 3 -->
<iframe src="https://player.vimeo.com/video/YOUR_VIMEO_VIDEO_ID_3" ...>
```

#### C. Customize Video Titles and Descriptions (Optional)

Find these sections and update the text:
- Line 398-400: Part 1 title and description
- Line 411-413: Part 2 title and description  
- Line 424-426: Part 3 title and description

### 3. Add to WordPress/Elementor

**Option A: Using Elementor HTML Widget**
1. Edit your page in Elementor
2. Drag an "HTML" widget onto the page
3. Paste the entire contents of `video-course.html` into the widget
4. Click "Update" to save

**Option B: Using Custom Code Section**
1. Go to your WordPress admin panel
2. Navigate to the page where you want to add the course
3. Find the custom code section
4. Paste the entire contents of `video-course.html`
5. Save the page

### 4. Optional: Add Your Logo

To add your organization's logo to the certificate:

1. Upload your logo to WordPress Media Library
2. Note the image URL
3. In the HTML, find the `generateCertificate()` function (around line 553)
4. Add this code inside the `cert-header` div:

```html
<img src="YOUR_LOGO_URL" alt="Logo" style="max-width: 150px; margin-bottom: 20px;">
```

## How It Works

### Password Protection
- When users first visit the page, they see a password overlay
- After entering the correct password, they gain access to all three videos
- The overlay uses a smooth animation and blur effect

### Video Progress Tracking
- Each video tracks playback progress in real-time
- Progress bars update as users watch
- Once a user reaches 90% completion, the video is marked as complete

### Certificate Generation
- After completing all three videos (90%+ each), a certificate section appears automatically
- Users enter their name
- Click "Generate Certificate" to see a preview
- Click "Download Certificate PDF" to save it to their device

### Responsive Design
- Automatically adjusts for mobile phones, tablets, and desktop
- Videos remain properly sized on all devices
- Touch-friendly buttons and inputs

## Customization Options

### Change Colors

In the CSS (lines 11-17), you can modify:
```css
:root {
    --cream: #fffaf3;      /* Background color */
    --magenta: #d7127b;    /* Primary accent */
    --purple: #ba94c4;     /* Secondary accent */
    --yellow: #fff46d;     /* Tertiary accent */
    --sage: #a8c89b;       /* Success color */
    --text-dark: #2d2d2d;  /* Text color */
}
```

### Change Completion Threshold

In the JavaScript (line 529), change `0.9` to a different value:
```javascript
if (data.percent >= 0.9 && !videoProgress[videoId + '_completed']) {
```
- `0.9` = 90%
- `0.95` = 95%
- `1.0` = 100%

### Modify Certificate Text

Find the `generateCertificate()` function and edit the HTML template to change:
- Certificate title
- Body text
- Footer text
- Signature lines

## Troubleshooting

### Videos Not Loading
- Check that your Vimeo video IDs are correct
- Make sure videos are set to "Public" or "Unlisted" in Vimeo settings
- Ensure embed settings are enabled in Vimeo

### Password Not Working
- Check that you've changed `COURSE_PASSWORD` in the JavaScript
- Password is case-sensitive
- Make sure there are no extra spaces

### Certificate Not Appearing
- Ensure all three videos reach 90% completion
- Check browser console for JavaScript errors
- Try refreshing the page

### PDF Download Issues
- The jsPDF library must load properly (included via CDN)
- Check your internet connection
- Some browsers may block automatic downloads - check permissions

## Browser Compatibility

Tested and working on:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome)

## Files Included

- `video-course.html` - Main HTML file with all code
- `README.md` - This file with instructions
- Logo placeholder (add your own)

## Support

If you need to make changes:
1. Edit the HTML file
2. Re-paste it into WordPress/Elementor
3. Clear your browser cache to see changes

## Future Enhancements

Potential additions you could request:
- User login/registration system
- Database storage of progress
- Multiple course support
- Email certificate delivery
- Quiz before certificate
- Social media sharing
- Integration with Learning Management Systems

---

**Note:** Remember to test everything with your actual Vimeo videos before sharing with clients!