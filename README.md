# Abdirauf Hassan — Portfolio Site

A single-file personal portfolio site: cybersecurity/CS work, DecodeLabs training projects, and long-form essays (published under the pen name Sibiyan), all in one page.

## File

- `abdirauf-hassan-portfolio.html` — the entire site. One HTML file, nothing else needed.

All four essay PDFs (Digital Detox, Ma'asalama Ya Ramadan, The Qur'an: A Foundation for Research, The 14th-Century Manual) are embedded inside this file as base64 data, so **Read** and **Download** work anywhere you open or host it — no separate PDF files to keep track of.

## How to use it

- **Open locally**: double-click the file, opens in any browser.
- **Host it**: upload `abdirauf-hassan-portfolio.html` as-is to GitHub Pages, Netlify, Vercel, or any static host. No build step, no dependencies to install.
- **GitHub Pages quick path**: rename it to `index.html`, push it to a repo, enable Pages on that repo — done.

## Structure

| Section | What's in it |
|---|---|
| Hero | Name, tagline, current focus |
| About | Bio — CS/security work + writing side |
| Experience | DecodeLabs training, volunteer work, KEMU |
| Projects | GitHub repos, pulled from `github.com/abdulrauf-8` |
| Writing | Substack essays, with Read/Download for the ones with PDFs |
| Contact | LinkedIn, GitHub, Instagram, X, Substack |

## Updating content

Everything is plain HTML/CSS/JS in one file — open it in any text editor.

- **Add a project**: copy one `.proj-card` block in the Projects section, edit the text and GitHub link.
- **Add an essay**: copy one `.write-card` block in the Writing section.
- **Add a downloadable PDF to an essay**:
  1. Base64-encode the PDF (`base64 -w0 yourfile.pdf`).
  2. Add an entry to the `window.PDF_DATA` object near the end of the file: `"someKey": "data:application/pdf;base64,<paste>"`.
  3. On the essay card, add:
     ```html
     <div class="w-actions">
       <button class="w-btn read" data-key="someKey" data-title="Essay Title">Read ↗</button>
       <a class="w-btn dl" data-key="someKey" download="Essay.pdf" href="#">Download ↓</a>
     </div>
     ```
- **Swap the color theme**: all colors are CSS variables at the top of the `<style>` block (`--ink`, `--gold`, `--wine`, `--green`, etc.) — change them once, they apply everywhere.

## Notes

- No backend, no build tools, no npm install. It's intentionally dependency-free so it never breaks.
- Fonts (Fraunces, Source Serif 4, JetBrains Mono, Inter) load from Google Fonts — needs an internet connection to render with the right typefaces; falls back to system fonts offline.
- Mobile responsive, keyboard-accessible, respects reduced-motion settings.
