# Dynamic Resume Builder

A small Flask web app that turns a form (with optional photo) into a styled, downloadable `.docx` resume.

## Project Structure

```
Dynamic-Resume-Builder/
├── app.py                  # Flask entry point
├── resume_builder/         # Resume generation package
│   ├── __init__.py
│   └── builder.py          # DOCX generation logic
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

## Author

**Ishan Chakraborty**

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.
