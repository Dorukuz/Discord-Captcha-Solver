
# Discord hCaptcha AI Solver

A powerful AI-based hCaptcha solver API designed specifically for Discord bot automation. This project provides a FastAPI web server running a fine-tuned Dutch language transformer model to automatically answer hCaptcha accessibility challenges in Dutch.

---
# 🔥 NEW: API-Based hCaptcha Solver!
Works like CapMonster & 2Captcha
€50/month | €200 lifetime | Source Code: €1200
Fast. Reliable. Easy.
https://t.me/dorukuz


https://github.com/user-attachments/assets/4eb3d40f-3228-4159-82c4-6fce5fbea371


## Features

- Uses a custom fine-tuned [RobBERT](https://huggingface.co/DTAI-KULeuven/robbert-2022-dutch-base) Dutch language model for high accuracy.
- Caches previous answers for ultra-fast response times.
- Simple REST API with a `/solve` endpoint accepting hCaptcha questions and returning AI-generated answers.
- Built with FastAPI for asynchronous and high-performance serving.
- Ideal for integrating into Discord bots that need to bypass hCaptcha accessibility challenges.

---

## How It Works

When the solver receives a question from the hCaptcha accessibility challenge (usually a simple Dutch "Ja" or "Nee" question), it:

1. Cleans and preprocesses the question text.
2. Checks if it already answered this question before — if yes, returns the cached answer.
3. Otherwise, it uses the transformer model pipeline to classify the answer as "Ja" (Yes) or "Nee" (No).
4. Logs the new question and answer for future caching.
5. Returns the answer in JSON format.

---

## API Usage

Send a POST request with JSON body:

```json
{
  "question": "Your hCaptcha question text here"
}
```

Response:

```json
{
  "question": "Your hCaptcha question text here",
  "answer": "Ja" // or "Nee"
}
```

---

## Integration Example in Discord Bots

In your Discord automation code, after detecting the accessibility challenge, you can send the question text to the local solver API, get the AI's answer, and fill it into the captcha input field automatically. This significantly speeds up and automates solving hCaptcha challenges during Discord account generation or bot registration.

Example workflow:

- Detect hCaptcha accessibility challenge frame.
- Extract the question text.
- POST to `http://localhost:8000/solve` with the question.
- Receive "Ja" or "Nee" answer.
- Fill the answer into the captcha input box.
- Submit and continue.

---

## Installation

1. Clone this repository:

```bash
git clone https://github.com/Dorukuz/Discord-Captcha-Solver.git
cd discord-hcaptcha-ai-solver
```

2. Create and activate a Python virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run the server:

```bash
python app.py
```

The API server will start at `http://0.0.0.0:8000`.

---

## Why Choose This Solver?

- Trained specifically on Dutch accessibility questions used in hCaptcha.
- Designed to handle Discord's hCaptcha challenges efficiently.
- Lightweight and easy to deploy locally or on a server.
- Extensible for further fine-tuning or adding support for other languages.

---

## License

This repository and code are for demonstration and paid use only. Unauthorized commercial use is prohibited.

---
## Contact

For subscription plans, commercial use, or custom integration support, contact:  
[My own Telegram](https://t.me/dorukuz) 

[AXI DEV Telegram Group](https://t.me/axi1337) 

---

*This project is a cutting-edge AI assistant helping Discord automation workflows handle hCaptcha challenges with ease.*
