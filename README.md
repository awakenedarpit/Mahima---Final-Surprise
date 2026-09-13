# 🎂 Final Birthday Surprise

An interactive birthday microsite built with **vanilla HTML, CSS, and JavaScript** — designed as a tap-through digital experience rather than a traditional birthday webpage.

The experience combines animated story slides, a passcode-protected opening, interactive wishes, background music, a gift-opening sequence, six collectible letters, and a final celebration.

> Built with AI-assisted development using Claude AI and ChatGPT, then customized, debugged, and crafted by **Awakenedarpit**.

## ✨ Highlights

- 🔐 Four-digit passcode-protected opening screen
- 🎨 Light/dark theme with gradients, particles, balloons, flowers, stars, petals, and confetti
- 📸 Interactive photo and memory sections
- 💭 Birthday wish selection with an optional secret wish
- 📧 EmailJS-powered wish submission
- 🎁 Interactive gift-opening experience
- 💌 Six interactive letters with a sequential unlock mechanic
- 🎵 Background music with browser-friendly user-interaction playback
- 📱 Responsive design for desktop and mobile
- ♿ Reduced-motion support for users who prefer less animation
- 🚀 Static deployment — no framework, build step, or application server required

## 🌸 Experience Flow

1. **Passcode Screen** — Enter the four-digit code to begin.
2. **Introduction** — A personalized animated birthday message.
3. **Memories** — Photo-wall and appreciation sections.
4. **Wish Ceremony** — Select wishes and optionally write a secret wish.
5. **Wish Transition** — Wishes travel into an animated night-sky sequence.
6. **Gift & Letters** — Open the gift to reveal six letters.
7. **Letter Unlock** — The sixth letter becomes available after the first five are opened.
8. **Final Celebration** — Complete the experience with the birthday finale.

## 🛠️ Tech Stack

- **HTML5** — structure and content
- **CSS3** — responsive layout, themes, animations, and visual effects
- **JavaScript** — interactions, navigation, state management, audio, letters, wishes, and effects
- **EmailJS** — client-side wish delivery
- **Google Fonts** — Fredoka & Quicksand

No npm dependencies or compilation step are required.

## 📁 Project Structure

```text
Final-Birthday-Surprise/
├── index.html      # Page markup, content, inline JavaScript, and EmailJS setup
├── bday.css        # Themes, responsive layout, animations, and component styles
├── images/         # Birthday and memory photos used by the experience
│   ├── m1.jpg
│   ├── m2.jpg
│   ├── m3.jpg
│   ├── p1.jpg
│   ├── p2.jpg
│   ├── p3.jpg
│   ├── p4.jpg
│   └── p5.jpg
├── music.mp3       # Background music
├── F.mp3           # Additional bundled audio asset
└── README.md       # Documentation
```

The image assets referenced by the current HTML are included in the repository under `images/`, so the photo sections can load correctly when the project is deployed with the complete repository.

## 🚀 Run Locally

### VS Code + Live Server

1. Clone or download this repository.
2. Open the project folder in Visual Studio Code.
3. Install the **Live Server** extension if needed.
4. Right-click `index.html`.
5. Select **Open with Live Server**.

### Python

From the project directory:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

## 📱 Mobile Testing

For the best mobile experience, deploy the complete repository to a static host and open the HTTPS URL on your phone.

When testing on mobile:

- Tap the page once so the browser can allow background audio.
- Test the passcode keypad using touch.
- Test portrait and landscape orientations.
- Confirm all images and audio assets load correctly.
- Use HTTPS when testing EmailJS.

## 🎨 Customization

Most personalization is inside `index.html`, while visual styling is primarily handled by `bday.css`.

### Change the passcode

Search for:

```js
const PASSCODE = "1308";
```

and replace the value with your preferred four-digit code.

### Change images

Replace the files inside `images/` while keeping the existing filenames, or update the corresponding `src` paths in `index.html`.

### Change music

The main background track is loaded from:

```html
<source src="music.mp3" type="audio/mpeg">
```

Replace `music.mp3` with another compatible MP3 or update the source path.

### Change themes and colors

The main design tokens are CSS custom properties near the beginning of `bday.css`. Update those variables to change the visual identity without rewriting individual components.

### Edit the letters

The six letter messages are stored in the JavaScript data structure inside `index.html`. Update the titles and messages while preserving the existing letter state and unlock logic.

## 📧 EmailJS Setup

The wish form uses EmailJS from the browser.

The implementation expects:

```js
const EMAILJS_PUBLIC_KEY  = "your-public-key";
const EMAILJS_SERVICE_ID  = "your-service-id";
const EMAILJS_TEMPLATE_ID = "your-template-id";
```

To configure it:

1. Create an EmailJS account.
2. Connect an email service.
3. Create an email template using the variables used by the page, including `selected_wishes` and `secret_wish`.
4. Add the EmailJS public key, service ID, and template ID to `index.html`.
5. Test the wish form over HTTP/HTTPS.

The EmailJS public key is intended for browser-side use. **Never put private API keys, passwords, or other secrets in client-side code.**

## 🌐 Deployment

This is a static website and can be deployed to services such as:

- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages
- Any static web server

Before deployment:

1. Ensure `index.html`, `bday.css`, `images/`, and the audio assets are included.
2. Check file-name capitalization — Linux-based hosts are case-sensitive.
3. Configure EmailJS if the wish-delivery feature is required.
4. Deploy over HTTPS.
5. Test the complete experience on both desktop and mobile.

## 🔒 Security & Privacy Notes

The passcode is a **front-end interaction, not secure authentication**. Anyone who can inspect the page source can discover or modify the client-side passcode logic.

Wish text entered by a visitor is sent through the configured EmailJS service. If the project is shared publicly, make sure the recipient understands what information is transmitted and where it is sent.

## 🤖 AI-Assisted Development

AI tools were used during development for ideation, implementation assistance, debugging, iteration, and refinement.

The final experience was **customized and crafted by Awakenedarpit**, with manual decisions around the UI, interactions, content, structure, assets, and behavior.

## 👨‍💻 Credits

Created with the help of **Claude AI** and **ChatGPT**.

Customized & crafted by **Awakenedarpit**.

- GitHub: [@awakenedarpit](https://github.com/awakenedarpit)
- Project: [Final-Birthday-Surprise](https://github.com/awakenedarpit/Final-Birthday-Surprise)

## 📄 License

No license file is currently included. Unless a license is added, the source should be treated as **all rights reserved**.


<!-- awakenedarpit-credits-contact -->
## 📬 Contact

This project was created and is maintained by **Arpit Raj** ([@awakenedarpit](https://github.com/awakenedarpit)). For questions, suggestions, or collaboration, reach out through [GitHub](https://github.com/awakenedarpit) or open an issue in this repository.

<!-- awakenedarpit-social-contact -->
### Connect with Arpit

- Instagram: [@awakenedarpit](https://www.instagram.com/awakenedarpit/)
- LinkedIn: [Arpit Raj](https://www.linkedin.com/in/awakenedarpit/)
- Email: [awakenedarpit@gmail.com](mailto:awakenedarpit@gmail.com)

<!-- awakenedarpit-twitter-contact -->
- Twitter/X: [@awakenedarpit](https://x.com/awakenedarpit)
