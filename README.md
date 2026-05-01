# BabelFish AI: Real-time Voice-to-Voice Translator

BabelFish AI is a full-stack translation assistant that integrates state-of-the-art Generative AI with Speech-to-Text (STT) and Text-to-Speech (TTS) services. By orchestrating multiple APIs, the application allows users to input English audio and receive a natural, translated vocal response in Spanish.

## The Tech Stack
* Backend: Python 3.11, Flask
* AI Engine: IBM Watsonx.ai (LLM: mistral-medium-2505)
* Cognitive Services: Watson Speech-to-Text, Watson Text-to-Speech
* Tools: Git, Virtual Environments (venv), Requests (HTTP orchestration)

## Key Features and Implementation
* LLM Orchestration: Integrated IBM Watsonx via the ibm-watson-machine-learning SDK to handle complex translation logic with strict formatting constraints.
* Prompt Engineering: Developed optimized system prompts to ensure the LLM returns direct translations without conversational filler, reducing latency and parsing errors.
* Bi-directional Speech Processing:
    * STT: Converts raw audio binary data from the browser into text using the Watson Multimedia model.
    * TTS: Synthesizes translated Spanish text into high-fidelity .wav audio files.
* Full-Stack Integration: Built a Flask API to manage the data flow between the frontend interface and the AI backend.

## Architecture Overview
The application follows a linear processing pipeline:
1. Capture: The frontend records user audio and sends the binary data to the Flask server.
2. Transcription: The speech_to_text module sends the audio to the Watson STT API.
3. Inference (Translation): The transcript is sent to the Watsonx Mistral-Medium model with a specific translation prompt.
4. Synthesis: The translated text is sent to the Watson TTS API.
5. Playback: The final audio content is returned to the browser for immediate playback.

## Project Structure
\`\`\`text
├── server.py          # Flask application and API endpoints
├── worker.py          # Core AI logic (Watsonx, STT, and TTS functions)
├── requirements.txt   # Project dependencies
├── static/            # Frontend assets (JavaScript, CSS)
└── templates/         # HTML structure
\`\`\`

## Setup and Installation

### 1. Prerequisites
* Python 3.11+
* Virtual Environment (recommended)

### 2. Installation
Clone the repository:
\`\`\`bash
git clone https://github.com/YOUR_USERNAME/babel-fish-ai-translator.git
cd babel-fish-ai-translator
\`\`\`

### 3. Running the Application
Start the Flask server:
\`\`\`bash
python3 server.py
\`\`\`
The application will be available at http://localhost:8000.

## Impact
This project demonstrates the ability to build production-ready AI pipelines, focusing on low-latency response times and clean API integration. It showcases expertise in:
* Handling Binary Data: Managing audio streams between client and server.
* Cloud AI Services: Working with enterprise-grade AI platforms like IBM Watsonx.
* Robust Programming: Writing clean, modular Python code that separates concerns between worker modules and the server interface.

---

