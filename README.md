# xxjordan.com — setup notes

## Deploying
Keep `index.html`, `styles.css`, `script.js`, and the `assets/` folder together —
same structure, same relative paths. For GitHub Pages: commit all of it to your
repo (root, or a `/docs` folder if that's what Pages is set to serve) and enable
Pages in the repo settings.

## Getting access to "Get in touch" emails — REQUIRED SETUP
GitHub Pages only serves static files, so the contact form can't run its own
backend to save submissions. It's wired up to **Formspree** instead — a free
service that receives the form submission and gives you a dashboard + email
notification. Right now it's pointed at a placeholder and **won't capture
anything until you finish this**:

1. Go to https://formspree.io and sign up (free plan is enough for this).
2. Create a new form. Formspree gives you an endpoint that looks like:
   `https://formspree.io/f/abcdwxyz`
3. Open `index.html`, find the `<form class="cta__form" ...>` tag (search for
   `YOUR_FORM_ID`), and replace `YOUR_FORM_ID` with the ID Formspree gave you.
4. Commit and push. Submit a test message through the live site to confirm it
   arrives.

**Once set up, here's how you access the emails:**
- **Instant**: Formspree emails you a copy of every submission as it comes in.
- **Anytime**: log in at formspree.io → your form → Submissions tab shows every
  entry, with an option to export as CSV.

Until step 3 is done, the form will show a message on-page saying it isn't
connected yet — it won't silently lose submissions, but it also won't send
you anything, so don't skip this.

## Logo
`assets/logo.png` is a background-removed version of the original logo (the
JPEG had a white background baked in) so it blends cleanly on any section.
The original JPEG is no longer referenced anywhere in the site.
