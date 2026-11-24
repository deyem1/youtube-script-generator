# YouTube Script Generator 🦜🔗🎬

A Streamlit app that turns a single topic into a YouTube **title and full script**. It chains two LLM calls with LangChain and grounds the script in live Wikipedia research.

## How it works

```
topic ──▶ [Title chain] ──▶ title ──┐
                                    ├──▶ [Script chain] ──▶ script
topic ──▶ Wikipedia API ──▶ research┘
```

- **`PromptTemplate` + `LLMChain`**: one chain writes the title, a second writes the script
- **`WikipediaAPIWrapper`**: pulls background facts so the script isn't purely invented
- **`ConversationBufferMemory`**: keeps a history of titles and scripts in the session

## Run it

```bash
git clone https://github.com/deyem1/youtube-script-generator.git
cd youtube-script-generator
pip install streamlit langchain openai wikipedia

streamlit run app.py
```

Put your OpenAI key in `apikey.py` (`apikeys = 'sk-...'`) before running, and never commit the real key.

## Tech

Python · LangChain · OpenAI API · Streamlit · Wikipedia API
