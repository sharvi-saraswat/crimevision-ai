# 🕵️ CrimeVision AI: Intelligent Multimodal Forensic Analysis Platform

**Skill Wallet Capstone Project 2** · Generative AI · Computer Vision · Speech · RAG

🔗 **Live Demo:** https://crimevision-ai-799zxiszgbwfm9vinep9l7.streamlit.app/

CrimeVision AI turns crime scene photos, witness audio and CCTV footage into one searchable, time-ordered evidence ledger. Investigators can then question the evidence in plain language, with every answer tied to an evidence ID, and export a forensic summary PDF.

> ⚠️ AI output is investigative support, not proof of guilt. Demo mode uses simulated data. All findings need human review.

## ✨ Features

- **Configuration & Security:** masked Groq/Gemini API key input, automatic demo fallback, and chain-of-custody indicators (Evidence ID, SHA-256, timestamp, investigator sign-off).
- **Scene Tagger:** upload a crime scene photo to detect persons, firearms, edged weapons, blood spatter and forced entry points, with confidence scores and coordinates. It also gives a Threat Level (Low to Critical), a Scene Classification (Burglary, Homicide, Vandalism, Assault) and prioritized investigative leads.
- **Witness Audio:** transcribes witness statements or 911/112 calls, with speaker tags, timestamped markers and key-event extraction.
- **CCTV Analysis:** samples video frames, tracks suspect and vehicle movement with OpenCV, and builds a chronological event log with indicative penal categories.
- **Fusion & Evidence Chat:** merges image, audio and video events into one master ledger. A grounded chat answers only from the ledger, cites evidence IDs, and says "Insufficient evidence" when the ledger has no answer.
- **PDF Export:** one-click forensic summary report built with ReportLab, with a custody registry, annotated image, event ledger, ledger hash and signature block.

## 🛠️ Tech Stack

Python · Streamlit · OpenCV · Pillow · Pandas · NumPy · ReportLab · Groq API · Google Gemini API

No external database is needed. All data lives in the Streamlit session, so the app deploys easily on Streamlit Community Cloud.

## 🚀 Run Locally

```bash
git clone https://github.com/sharvi-saraswat/crimevision-ai.git
cd crimevision-ai
pip install -r requirements.txt
streamlit run app.py
```

Without an API key the app runs in demo mode. For live mode, enter a Groq or Gemini key in the sidebar.

## 📖 How to Use

1. Enter the Case ID and investigator name in the sidebar, then tick the sign-off box.
2. Upload evidence in Tabs 1 to 3 (photo, audio, video) and run the analysis.
3. Open Tab 4 to see the master ledger and ask questions such as "Was a weapon visible before the suspect fled?"
4. Open Tab 5 and generate the forensic PDF report.

## 🔒 Design Principles

- **Grounded answers:** chat uses only ledger entries, and citations to non-existent IDs are rejected.
- **Auditable rules:** threat level and scene classification come from transparent rules.
- **Chain of custody:** every file is hashed (SHA-256) and logged with a timestamp and custodian.

## 📌 Disclaimer

Built for educational and demonstration purposes only. Legal categories shown are indicative and must be confirmed by qualified counsel.
