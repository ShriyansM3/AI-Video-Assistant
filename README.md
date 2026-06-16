# AI Video Assistant with RAG

An AI-powered meeting assistant that processes YouTube videos and local audio/video files to generate transcripts, summaries, action items, key decisions, and context-aware question answering using Retrieval-Augmented Generation (RAG).

## Features

- Accepts YouTube URLs and local audio/video files as input
- Transcribes English audio using Whisper
- Supports Hinglish transcription using Sarvam AI
- Generates concise meeting summaries
- Extracts action items, key decisions, and open questions
- Enables conversational Q&A over meeting transcripts using RAG
- Provides an interactive web interface built with Streamlit

## Tech Stack

- Python
- LangChain (LCEL)
- Whisper
- Sarvam AI
- Mistral AI
- ChromaDB
- HuggingFace Embeddings
- Streamlit
- yt-dlp
- pydub

## How It Works

1. Input a YouTube URL or local media file.
2. The application extracts and preprocesses the audio.
3. Audio is transcribed using Whisper or Sarvam AI based on the selected language.
4. The transcript is analyzed to generate:
   - Meeting title
   - Summary
   - Action items
   - Key decisions
   - Open questions
5. The transcript is converted into embeddings and stored in ChromaDB.
6. Users can ask natural-language questions that are answered using retrieval over the meeting transcript.

## Project Structure

```text
AI-Video-Assistant/
├── app.py
├── main.py
├── core/
│   ├── transcriber.py
│   ├── summarizer.py
│   ├── extractor.py
│   ├── rag_engine.py
│   └── vector_store.py
├── utils/
│   └── audio_processor.py
└── requirements.txt
```

## Installation

```bash
git clone <repository-url>
cd AI-Video-Assistant
pip install -r requirements.txt
```

Create a `.env` file and add the required API keys:

```text
MISTRAL_API_KEY=your_api_key
SARVAM_API_KEY=your_api_key
WHISPER_MODEL=small
```

Run the application:

```bash
streamlit run app.py
```

## Future Improvements

- PDF and TXT report export
- Speaker diarization
- Support for additional languages
- Persistent meeting history
- Cloud deployment

