# Saathi: an AI companion for mental health screening and support

> *"You don't have to figure it out alone."*

**SDG 3: Good Health and Well-being** (Target 3.4: promote mental health and well-being)
Built for **IBM SkillsBuild, Masterclass 5: Creating Real-Life Projects**.

> **Important:** Saathi is a screening and support concept. It does **not** diagnose, treat, or replace a counsellor, doctor or therapist. If you or someone you know is in danger or thinking of self-harm, contact local emergency services or a helpline right away (for example, Tele-MANAS in India: **14416**, please verify current details).

*"Saathi" means "companion" in Hindi and Odia.*

---

## The problem

Many young people feel stressed, anxious or low and never talk to anyone about it. Stigma, cost, and a shortage of counsellors, especially outside big cities, mean help often arrives late or not at all. Many people also can't tell whether what they feel is "serious enough" to ask for help.

## Our solution

A private, friendly chatbot (English, Hindi, Odia; WhatsApp and web) that:

1. **Checks in** with a warm, conversational mood check.
2. **Screens** using validated questionnaires (PHQ-9 for low mood, GAD-7 for anxiety). Scores come from **transparent rules, not AI guesses**.
3. **Supports** with simple self-care: breathing, grounding, journaling, sleep tips.
4. **Refers** to counsellors and helplines when more help is needed, with a **crisis protocol** for urgent situations.

## Who it helps

Students and young adults (16-29), starting with colleges and Tier-2/3 cities. Campus counsellors and NGOs benefit from anonymised, aggregate insights.

## How it works

```
Check-in  ->  Screening (PHQ-9 / GAD-7)  ->  Support (self-care)  ->  Referral
                      |
                      +--> Crisis signals --> stop normal flow --> care + emergency contacts
```

| Layer | What it does | Why |
|---|---|---|
| Language model *(planned)* | Warm conversation, tone and distress cues | Natural, human-feeling check-ins |
| **Rule-based scoring** *(in this repo)* | Scores PHQ-9 / GAD-7 using published cut-offs | Transparent, auditable, no AI guesswork |
| **Crisis safeguards** *(in this repo)* | Detects PHQ-9 item 9 and crisis phrases; returns fixed, human-written responses | Safety is never left to a model |
| Clinician-reviewed content | Self-care scripts and referral guidance | Quality and cultural fit |

## SDG 3 alignment

Saathi widens access to early mental health support, lowers the stigma of the first conversation, and helps people reach professional care sooner.

## What's in this repo

```
.
├── README.md
├── LICENSE
├── requirements.txt
├── docs/
│   ├── submission/            # Lean Canvas (PDF), Concept Note, Presentation, One-Pager
│   ├── ETHICS_AND_SAFETY.md
│   └── ROADMAP.md
├── src/saathi/
│   ├── screening.py           # PHQ-9 / GAD-7 questions, scoring, severity bands
│   ├── crisis.py              # Crisis detection and fixed safety response
│   ├── selfcare.py            # Simple self-care suggestions
│   └── cli.py                 # Text-based demo
└── tests/
    └── test_screening.py
```

### Submission documents

| Document | File |
|---|---|
| Lean Canvas | [`docs/submission/Saathi_Lean_Canvas.pdf`](docs/submission/Saathi_Lean_Canvas.pdf) |
| Concept Note | [`docs/submission/Saathi_Concept_Note.docx`](docs/submission/Saathi_Concept_Note.docx) |
| Presentation | [`docs/submission/Saathi_Presentation.pptx`](docs/submission/Saathi_Presentation.pptx) |
| Project One-Pager | [`docs/submission/Saathi_Project_One_Pager.pdf`](docs/submission/Saathi_Project_One_Pager.pdf) |

## Try the prototype

Requires Python 3.9+. No external packages needed.

```bash
git clone https://github.com/<your-username>/saathi-ai-mental-health.git
cd saathi-ai-mental-health
python -m src.saathi.cli        # run the demo
pip install pytest && pytest    # run the tests
```

The demo walks through a short check-in, scores the PHQ-9 or GAD-7, shows a gentle summary with self-care ideas, and shows the crisis response if needed. **It is a prototype for learning and demonstration, not a clinical tool.**

## Ethics and privacy (summary)

- Clearly states it is **not** a diagnosis or therapy.
- Explicit consent; anonymised, encrypted data; users can delete their data. No data selling, no ads.
- Fixed, human-approved crisis responses; helpline hand-off.
- Regular bias checks across languages, genders and regions.

Details: [`docs/ETHICS_AND_SAFETY.md`](docs/ETHICS_AND_SAFETY.md)

## Roadmap

| Phase | Timing | Focus |
|---|---|---|
| 1 | Months 0-3 | Co-design with students and counsellors; prototype |
| 2 | Months 3-6 | Pilot in 1-2 colleges; test safety responses |
| 3 | Months 6-12 | More languages, counsellor dashboard, NGO and helpline partners |

Details: [`docs/ROADMAP.md`](docs/ROADMAP.md)

## Impact metrics

Users screened · repeat check-ins · referrals made · comfort and helpfulness ratings · crisis hand-offs handled safely.

## Team

| Name | Role |
|---|---|
| [Name] | [Role] |
| [Name] | [Role] |
| [Name] | [Role] |
| [Mentor name] | Mentor / advisor |

## Acknowledgements

- PHQ-9 and GAD-7 were developed by Drs. Robert L. Spitzer, Janet B.W. Williams, Kurt Kroenke and colleagues, and are free to use.
- IBM SkillsBuild for the project framework.

## License

[MIT](LICENSE)
