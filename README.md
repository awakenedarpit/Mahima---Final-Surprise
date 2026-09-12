Final BirthDay Surprise

A tap-through birthday experience built with vanilla HTML, CSS and JS. Five story slides, ambient particles, a blow-out-the-candles interaction and a confetti finale.

A Interactive birthday microsite built with **vanilla HTML, CSS, and JavaScript**. The experience is designed as a tap-through celebration: a passcode-protected opening screen leads into animated story slides, wish selection, an EmailJS-powered message flow, a surprise letter collection, and a final birthday celebration.

> This project is a static front-end experience. It does not require a framework, build step, package manager, or application server.

## Contents

- [Highlights](#highlights)
- [Experience flow](#experience-flow)
- [Project structure](#project-structure)
- [Requirements](#requirements)
- [Run locally](#run-locally)
- [Use on a phone](#use-on-a-phone)
- [Customization](#customization)
- [EmailJS configuration](#emailjs-configuration)
- [Media and image assets](#media-and-image-assets)
- [Architecture](#architecture)
- [Browser compatibility](#browser-compatibility)
- [Troubleshooting](#troubleshooting)
- [Deployment](#deployment)
- [Security and privacy notes](#security-and-privacy-notes)
- [Credits](#credits)
- [License](#license)

## Highlights

| Area | Included behavior |
| --- | --- |
| Presentation | Animated, responsive birthday story with multiple full-screen stages |
| Access | Four-digit numeric passcode screen before the surprise begins |
| Navigation | Tap/click controls, keyboard support, progress indicators, and slide transitions |
| Visual design | Light and dark themes, gradients, balloons, particles, flowers, stars, petals, and confetti |
| Interaction | Wish selection, secret-wish text input, animated night-sky sequence, gift opening, and letter unlocking |
| Letter collection | Six interactive letters; the sixth letter becomes available after the first five are opened |
| Audio | Background music from `music.mp3`, started after the first user interaction to satisfy browser autoplay rules |
| Delivery | Can be opened through a local static server or deployed to any static hosting provider |

## Experience flow

The current implementation follows this sequence:

1. **Passcode screen** — The visitor sees a birthday gift and enters the four-digit code.
2. **Introduction** — A personalized birthday message is shown with animated background decorations.
3. **Memory and appreciation slides** — Photo areas, compliments, reasons, and decorative effects create the main story section.
4. **Wish ceremony** — The visitor selects one or more wishes and may enter a private message.
5. **Wish transition** — Selected wishes animate away, followed by stars, a shooting star, and a continuation prompt.
6. **Gift and letters** — The visitor opens the gift to reveal six letters. Each letter opens in a modal-style viewer with a typewriter effect and falling petals.
7. **Unlock sequence** — After the first five letters have been opened, the sixth letter is unlocked with a key animation and confetti.
8. **Final celebration** — After all letters are read, the experience transitions to the final birthday celebration stage.

## Project structure

```text
Mahima---Final-Surprise/
├── index.html   # Page markup, inline JavaScript, content, and EmailJS setup
├── bday.css     # Theme variables, responsive layout, animations, and component styles
├── music.mp3    # Background music used by the page
├── F.mp3        # Additional bundled audio file; not referenced by the current HTML
└── README.md    # Project documentation
```

### Important repository note

The current `index.html` contains references to image files such as `images/p1.jpg`, `images/p2.jpg`, `images/m1.jpg`, and `images/hero.jpg`, but an `images/` directory is not included in the tracked repository at present. The corresponding image elements may therefore appear broken or empty until the expected files are added.

Expected image paths currently referenced by the HTML include:

```text
images/hero.jpg
images/p1.jpg
images/p2.jpg
images/p3.jpg
images/p4.jpg
images/p5.jpg
images/m1.jpg
images/m2.jpg
images/m3.jpg
```

To restore the photo sections, create an `images/` directory at the project root and add files with these exact names. Alternatively, remove or replace the image markup in `index.html`.

## Requirements

The project has no npm dependencies and no compilation step. You only need:

- A modern web browser such as Chrome, Edge, Firefox, or Safari.
- A local static server for reliable testing.
- An internet connection if you want Google Fonts or the EmailJS CDN integration to load.

Opening `index.html` directly with a `file://` URL may work for basic markup, but a local HTTP server is recommended because browser media, CDN, and JavaScript behavior can differ when a page is loaded from the filesystem.

## Run locally

### Option 1: VS Code Live Server

1. Clone or download this repository.
2. Open the project folder in Visual Studio Code.
3. Install the **Live Server** extension if it is not already installed.
4. Right-click `index.html`.
5. Select **Open with Live Server**.
6. Open the displayed local URL in your browser.

### Option 2: Python static server

From the project directory, run:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).

Stop the server with `Ctrl+C`.

### Option 3: Node.js static server

If you already use Node.js, any static server can host this directory. For example:

```bash
npx serve .
```

Follow the local URL printed by the command.

### Original quick-start instructions

The original project README provided the following beginner-friendly workflow:

**For laptop users:** download the HTML and CSS files or clone the repository, extract the files if downloaded as an archive, open the folder in Visual Studio Code, and use **Open with Live Server** on the HTML file.

**For mobile users:** copy the repository link, import the repository into [Replit](https://replit.com/), and open the generated project preview.

The local-server instructions above are recommended when you want predictable asset loading and easier debugging.

## Use on a phone

The most reliable mobile workflow is to deploy the repository to a static host and open the resulting HTTPS URL on the phone. You can also import the repository into an online development environment such as Replit and use its preview URL.

When testing on mobile:

- Tap the page once to allow background audio to begin.
- Use the on-screen number pad rather than relying on a physical keyboard.
- Test both portrait and landscape orientations.
- Confirm that every intended image is present in the deployed `images/` directory.
- Use HTTPS when testing EmailJS and any external resources.

## Customization

Most personalization is performed directly in `index.html`. Styling and color changes are primarily handled in `bday.css`.

The original README summarizes the main customization points as follows:

- Edit the text inside each `<section class="slide">` block to personalize the message.
- Change the colors through the CSS variables under `:root` in `bday.css`.
- Replace the emoji or add the recipient’s name for a more personal touch.

### Change the recipient and opening message

Update the visible text in the opening lock screen and the first slide. Search for text such as:

```html
<h1 class="name">
    My Friend
</h1>
```

and:

```html
<h1>Something Special For<em> My Favourite Person's</em> Birthday</h1>
```

You can also change the author line, headings, captions, compliments, and letter content in their respective HTML sections.

### Change the passcode

The passcode is defined in the inline JavaScript near the `PREMIUM PASSCODE SYSTEM` comment:

```js
const PASSCODE = "1308";
```

Replace the value with another four-digit string. Keep the value in quotes and ensure that the number of digit buttons and passcode indicators remains consistent with the desired experience.

### Edit wishes

The wish options are represented by elements with the `wish-cloud` class. Change their labels while preserving the class:

```html
<div class="wish-cloud" style="--d:0s;">💖 Endless Happiness</div>
```

The visitor must select at least one wish before the send action continues.

### Edit the letters

The six letter messages are stored in the JavaScript letters data structure. Search for the letter definitions and update each title and message. The sixth letter is intentionally locked until the first five letters have been opened.

### Change colors and themes

The primary design tokens are defined at the top of `bday.css` using CSS custom properties. The light theme includes variables such as:

```css
:root {
  --pink: #ff8fab;
  --lavender: #b79ced;
  --gold: #ffc266;
}
```

The dark theme overrides the same variables under the theme selector. Change the variables rather than editing individual components whenever possible.

### Change typography

The page loads **Fredoka** and **Quicksand** from Google Fonts. The font families are declared in the CSS variables near the beginning of `bday.css`. If the page must work without an internet connection, replace the remote font import with locally hosted fonts or system fallbacks.

### Replace music

The page currently uses `music.mp3` in its audio element:

```html
<source src="music.mp3" type="audio/mpeg">
```

To use another track, replace the file while keeping the same filename, or update the `src` value. The browser starts playback after the first click or touch because modern browsers commonly block unsolicited autoplay.

## EmailJS configuration

The wish form sends the selected wishes and optional secret wish through EmailJS. The EmailJS browser SDK is loaded from jsDelivr, and the page initializes it near the top of `index.html`.

The implementation expects three values:

```js
const EMAILJS_PUBLIC_KEY  = "your-public-key";
const EMAILJS_SERVICE_ID  = "your-service-id";
const EMAILJS_TEMPLATE_ID = "your-template-id";
```

To configure this feature:

1. Create an account at [EmailJS](https://www.emailjs.com/).
2. Create or connect an email service.
3. Create an email template containing the variables `selected_wishes` and `secret_wish`.
4. Copy the public key, service ID, and template ID into `index.html`.
5. Serve the project over HTTP or HTTPS.
6. Select a wish, optionally enter a secret wish, and verify that the configured inbox receives the message.

If EmailJS is not required, remove the EmailJS script and initialization code, then replace the send handler with a local success state or another backend integration.

## Media and image assets

The project includes two MP3 files. `music.mp3` is referenced by the page as background music. `F.mp3` is bundled in the repository but is not referenced by the current HTML, so it can be removed if it is no longer needed or wired into a separate audio element if intended for another part of the experience.

For image assets, preserve the relative paths used in `index.html`. Web hosts on Linux are case-sensitive, so `images/P1.jpg` and `images/p1.jpg` are different paths.

## Architecture

This is a deliberately simple static project:

- `index.html` contains the page structure, content, audio element, EmailJS initialization, and application logic.
- `bday.css` contains layout rules, responsive breakpoints, theme variables, component styles, and keyframe animations.
- JavaScript manages passcode validation, navigation, progress updates, theme switching, music playback, wish selection, night-sky effects, gift opening, letter state, typewriter rendering, petals, confetti, and final-stage transitions.
- External runtime dependencies are limited to Google Fonts and the EmailJS browser SDK loaded from CDNs.

No server-side code is included. Email delivery is handled by the third-party EmailJS service from the browser.

## Browser compatibility

The project uses standard browser APIs and modern CSS features, including:

- CSS custom properties.
- CSS animations and transitions.
- `backdrop-filter` where supported.
- `Audio` playback after user interaction.
- DOM event listeners and dynamically created elements.
- Responsive viewport units and media queries.

Current desktop and mobile browsers should support the core experience. Browsers without `backdrop-filter` will still render the page, but translucent cards may appear less blurred.

The page also includes a `prefers-reduced-motion` media query. Users who prefer reduced motion should receive a less animated presentation.

## Troubleshooting

| Problem | Likely cause | Resolution |
| --- | --- | --- |
| The page is blank or styles do not load | The project was opened from the wrong directory or the CSS path was changed | Confirm that `index.html` and `bday.css` are in the same directory and use a local HTTP server |
| Photos are missing | The tracked repository does not currently include the referenced `images/` directory | Add the expected image files or remove/update the image elements |
| Music does not start immediately | Browser autoplay policy | Tap or click once on the page; playback is intentionally started after user interaction |
| Wishes do not arrive by email | EmailJS identifiers, template variables, or network access are incorrect | Check the three EmailJS IDs, confirm the template variables, and inspect the browser console |
| The passcode does not work | The entered value does not match `PASSCODE` | Check the value in the passcode system and enter all four digits |
| Fonts look different | Google Fonts cannot be reached | Confirm internet access or configure local font files and fallbacks |
| The sixth letter stays locked | Fewer than five letters have been opened | Open the first five letters before attempting to open the sixth |
| Mobile layout overflows | Custom text or media is larger than the original content | Test at narrow widths and adjust the related CSS breakpoint or content length |

For deeper debugging, open the browser developer tools and inspect the **Console** and **Network** tabs. JavaScript errors, failed CDN requests, missing image files, and EmailJS failures are typically visible there.

## Deployment

Because the repository is static, it can be deployed to services such as GitHub Pages, Netlify, Vercel, Cloudflare Pages, or any web server that serves HTML, CSS, JavaScript, and media files.

A generic deployment checklist is:

1. Ensure `index.html`, `bday.css`, and the audio files are in the published directory.
2. Add the missing `images/` directory if the photo sections are intended to be used.
3. Verify that all paths use the correct capitalization. This matters on Linux-based hosts.
4. Configure the EmailJS values if wish delivery is required.
5. Deploy over HTTPS.
6. Test the passcode, audio, wishes, letters, and final celebration on both desktop and mobile.

### GitHub Pages

To publish through GitHub Pages, push the repository to GitHub, open **Settings → Pages**, choose the desired branch and root directory, and save. GitHub Pages will provide a public HTTPS URL after the deployment completes.

## Security and privacy notes

The passcode is a front-end interaction, not a secure authentication mechanism. Anyone who can inspect the page source can discover the passcode and change the client-side behavior.

The EmailJS public key and service/template identifiers are also used in browser-side code. Do not place passwords, private API keys, or other secrets in `index.html`. Use a server-side backend if the project must protect private data or enforce access control.

Any wish text entered by a visitor is transmitted to the configured EmailJS service. Update the interface and privacy notice as appropriate before sharing the site publicly.

## Credits

Created With the Help of Claude AI And ChatGPT, Customized & Crafted by **Awakenedarpit**.

Made by **@Awakenedarpit**.

- GitHub: [awakenedarpit/Final-Birthday-Surprise](https://github.com/awakenedarpit/Final-Birthday-Surprise)
- Instagram: [@Awakenedarpit](https://www.instagram.com/awakenedarpit?igsh=MWRpamlra3c5Ym1vcQ==)
- ## 📬 Contact

Feel free to reach out to me at **[awakenedarpit@gmail.com]** for any questions, collaborations, or opportunities.


## License

No license file is currently included in the repository. Unless the repository owner adds a license, the source should be treated as **all rights reserved**. Add a `LICENSE` file if you want others to have clearly defined permission to use, modify, or redistribute the project.

## References

[1]: https://github.com/awakenedarpit/Mahima---Final-Surprise "Mahima — Final Surprise repository"
[2]: https://www.emailjs.com/ "EmailJS documentation and service"
[3]: https://pages.github.com/ "GitHub Pages documentation"
