# MatchAI — Intelligent Resume Investigator

**ALG-AI-01** · Client-side AI-powered Resume & Job Matching System

A fully interactive, browser-based prototype that lets recruiters (or candidates) upload one or more resumes, paste a job description, and instantly receive ranked match analysis — complete with skill extraction, experience estimation, anomaly detection, ATS threshold filtering, and PDF export.

> **No backend. No API keys. Everything runs in the browser.**

---

## Features

### Core Matching Engine
- **Job Description input** — editable textarea with a realistic sample JD
- **Batch resume upload** — drag-and-drop or click to select up to **10 files** (`.txt` fully supported; `.pdf` / `.docx` accepted with limited extraction)
- **Sample resumes** — one-click load of three profiles (Strong Match, Partial Match, Irrelevant)
- **Dynamic analysis pipeline** with realistic progress steps:
  - Extracting text
  - Parsing contact details
  - Extracting skills & experience
  - Comparing against JD
  - Detecting anomalies
  - Ranking candidates

### Ranked Results Dashboard
- Overall match score (color-coded)
- Fit level (Excellent / Strong / Moderate / Weak / Poor)
- Executive AI summary
- Extracted profile (name, email, phone, estimated years of experience)
- **Matched skills** (green) vs **Skill gaps** (amber)
- Detailed criteria bars:
  - Technical Skill Fit
  - Experience Level Fit
  - Education & Certification Alignment
- Explainable match rationale (bullet points)
- Anomaly / unsupported-claim detection
- Collapsible raw extracted text

### ATS Threshold Filtering
- Interactive slider (0–100%, default **75%**)
- Live count of candidates who pass the threshold
- Optional “Show only candidates meeting threshold” filter
- PASS / BELOW badges on every candidate card

### PDF Export (Client-side)
- **Download Qualified Candidates Report** — batch PDF of everyone who meets the current ATS threshold
- **Download Summary PDF** — individual candidate match report (only for qualified candidates)
- Powered by `jsPDF` + `jspdf-autotable` (no server required)

### Design
- Clean modern SaaS aesthetic
- **White & Red** primary theme (`bg-red-600`, red focus rings, red accents)
- Responsive layout (works on desktop and tablet)

---

## Tech Stack

| Layer            | Technology                                      |
|------------------|-------------------------------------------------|
| UI               | React 18 (CDN)                                  |
| Styling          | Tailwind CSS (CDN)                              |
| Icons            | Lucide Icons                                    |
| PDF Generation   | jsPDF + jspdf-autotable                         |
| Runtime          | Single self-contained HTML file                 |
| Data             | 100% client-side (File API + regex heuristics)  |

No build step, no Node.js, no package manager required.

---

## How to Run

1. Download or clone this repository.
2. Open `matchai.html` in any modern browser (Chrome, Firefox, Edge, Safari).
3. That’s it.

```bash
# Optional: serve locally if you prefer
npx serve .
# then open http://localhost:3000/matchai.html
```

---

## Quick Start Demo

1. Open the app.
2. Click **Load 3 Sample Resumes**.
3. Watch the progress animation and ranked list appear.
4. Adjust the **ATS Score Threshold** slider.
5. Click any candidate to view the full analysis.
6. Click **Download Qualified Report (PDF)** or **Download Summary PDF**.

---

## File Structure

```
.
├── matchai.html          # Complete single-file application
└── README.md             # This file
```

---

## Browser Support

- Chrome / Edge (recommended)
- Firefox
- Safari

Requires a modern browser with support for:
- ES6+
- FileReader API
- Blob / download attributes

---

## Limitations (Prototype)

- Full text extraction is reliable for **`.txt`** files.
- **`.pdf`** and **`.docx`** are accepted but only metadata/placeholder text is shown (full extraction would require `pdf.js` / `mammoth.js`).
- Matching logic uses keyword + regex heuristics (not a real LLM). Suitable for demos and internal tools; not a production ATS replacement.
- All processing is local — no data is sent to any server.

---

## Future Ideas

- Real PDF/DOCX text extraction via `pdf.js` + `mammoth`
- Export to CSV / Excel
- Side-by-side candidate comparison
- Custom skill weight configuration
- Dark mode

---

## License

MIT License — feel free to use, modify, and distribute.

---

## Author

Built as a Principal Full-Stack React prototype for **ALG-AI-01**.

---

**MatchAI** — Intelligent Resume Investigator  
*Client-side · Instant · Explainable*
