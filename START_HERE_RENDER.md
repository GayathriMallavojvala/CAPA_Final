# Full Python application — Render deployment

This package preserves the original application, reference collections, simulations,
results, tests, diagnosis and effectiveness modules. Changes: deployment files,
continued inspection entry after a model threshold, visible invalid-result errors,
and user-only test-selection events to avoid clearing a result during panel updates.

## GitHub and Render
Upload the CONTENTS of this folder to a new repository or branch. Keep subfolders.
Use a NEW Render Web Service connected to that repository/branch, not the old Static Site.
Leave the old static service running until the new service is verified.

- Language: Python 3
- Root Directory: blank (app.py and requirements.txt at repository root)
- Build command: pip install -r requirements.txt
- Start command: python app.py
- Environment: PYTHON_VERSION=3.12.8, GRADIO_ANALYTICS_ENABLED=False
- No publish directory: this is a server application.

## LLM configuration
For the existing default Groq integration, add GROQ_API_KEY in Render's Environment
settings. Never place the value in GitHub. Default model: llama-3.1-8b-instant.
Alternatively set LLM_BASE_URL, LLM_MODEL and LLM_API_KEY for a compatible endpoint.
The model must be available in your provider account. An API key may require billing
or have rate limits. No live provider call was verified in this package.

Without credentials, diagnosis, storage and effectiveness calculations still work;
LLM drafting returns a configuration error. There is no invented LLM fallback.

## Storage
SQLite writes cases and actions to data/capa.db by default. On Render's ephemeral
filesystem runtime changes do NOT survive restarts or deployments. For persistent
storage attach a paid disk at /var/data and set CAPA_DB=/var/data/capa.db.
The supplied data/capa.db is preserved from the uploaded package; inspect existing
records before public deployment. There is no authentication: use demonstration
information only in this publicly accessible research prototype.

## First test
1. Open Guided Investigation; describe longitudinal scratches on a steel coil.
2. Start investigation, record an inspection, then record another available inspection.
3. Check Cases & Actions to see the saved evidence and audit trail.
4. Set your provider key, then generate the CAPA draft.
5. Open CAPA Effectiveness Lab to design and verify a monitoring window.

Run tests: python -m unittest discover -s tests -v

## Evidence and limits
Strict source-checked retrieval is preserved: the existing audit reports only one
eligible steel reference passage. NASA/FDA and unverified summaries remain in the
archive, but are not silently promoted to verified steel evidence. Add reviewed
sources through the registry to expand eligible retrieval. The benchmark data are
synthetic, not measured plant performance. Existing S/O/D scoring is not completed
by this restoration. The statistical effectiveness model needs validation and
assumes comparable production exposure for its weekly defect-count comparison.

Official hosting references:
https://render.com/docs/web-services
https://render.com/docs/disks

## Professional update
See PROFESSIONAL_UPDATE.md for formatted preview and fast verification mode.
