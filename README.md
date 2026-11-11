# Dynamic Resume Builder

A small Flask web app that turns a form (with optional photo) into a styled, downloadable `.docx` resume.

## Project Structure

```
Dynamic-Resume-Builder/
├── app.py                  # Flask entry point
├── resume_builder/         # Resume generation package
│   ├── __init__.py
│   ├── builder.py          # DOCX generation logic
│   └── linkedin.py         # LinkedIn OAuth + data-export import
├── templates/
│   └── index.html          # Web form UI
├── requirements.txt
├── LICENSE
├── .gitignore
└── README.md
```

## Getting Started

```bash
git clone https://github.com/<your-username>/Dynamic-Resume-Builder.git
cd Dynamic-Resume-Builder
python -m venv .venv
.venv\Scripts\activate        # Windows (source .venv/bin/activate on macOS/Linux)
pip install -r requirements.txt
python app.py
```

Then open <http://127.0.0.1:5000>.

## LinkedIn Import

LinkedIn has no open API for reading a full profile from its URL, and scraping violates its Terms of Service, so this app uses two supported routes:

1. **Upload your LinkedIn profile PDF (quickest, no setup).** On your LinkedIn profile click *More → Save to PDF*, then upload the `.pdf` in the form. Fields are filled by pattern-matching, so review them before generating.
2. **Upload your LinkedIn data export (most complete).** *Settings → Data privacy → Get a copy of your data* → request the archive → download the emailed `.zip` and upload it (no need to unzip). Headline, summary, experience, education, skills, certifications and projects are filled in.
3. **Connect with LinkedIn (optional, official OAuth).** Fills name, email and photo. Create an app at <https://www.linkedin.com/developers/apps>, add the *Sign In with LinkedIn using OpenID Connect* product, add `http://127.0.0.1:5000/auth/linkedin/callback` as a redirect URL, then:

```bash
set LINKEDIN_CLIENT_ID=your-id            # PowerShell: $env:LINKEDIN_CLIENT_ID="your-id"
set LINKEDIN_CLIENT_SECRET=your-secret
set SECRET_KEY=any-long-random-string
python app.py
```

The button only appears when these variables are set. The profile URL field is simply added to your resume.

## Author

**Ishan Chakraborty**

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.
