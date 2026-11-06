# How to host

## Option A: Hugging Face Space (free, easiest)
1. huggingface.co -> New Space -> SDK: Gradio -> create.
2. Upload ALL files in this folder (drag and drop in "Files"), keeping the folders.
3. Space -> Settings -> Variables and secrets -> New secret:
   name `GROQ_API_KEY`, value = your key from console.groq.com (free).
4. Wait for the build; open the app.

Note: free Spaces have temporary disk, so saved cases disappear when the Space restarts.
For lasting storage use Option B or add Hugging Face persistent storage.

## Option B: any server / Render / your laptop
    pip install -r requirements.txt
    GROQ_API_KEY=your_key python app.py        # opens on http://localhost:7860

## Private / on-prem model (plant data never leaves the network)
Set these instead of the Groq key, e.g. for Ollama:
    LLM_BASE_URL=http://localhost:11434/v1
    LLM_MODEL=llama3.1:8b
Other settings: `LLM_API_KEY` (not needed for local servers), `CAPA_DB` (database file path).
