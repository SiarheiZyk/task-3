# task-3: Self Teacher bot

Link: <https://t.me/selfteach_bot>

This bot is a Telegram-based AI tutor built with Telegram and automated using n8n.
It helps you save learning materials from URLs and automatically generate summaries and quizzes.

## Features

- 📚 Save articles from URLs
- 🧠 AI-generated summaries (5–7 key points)
- 📖 Extracted key concepts and definitions
- 🧪 Auto-generated quizzes (5 questions per topic)
- 📊 Score tracking and results
- 💬 Interactive inline buttons in Telegram

## Setup

1. Start the bot in Telegram

## How to use

### 1. Start the bot

Run command: **/start**

You will receive a welcome message and available commands.

### 2. Add learning material

Run command: **/learn [URL]**

Example: /learn <https://en.wikipedia.org/wiki/Learning>

What happens:

- The bot fetches the page content
- AI generates:
  - Title
  - Summary
  - Key points (5–7)
  - Main concepts
  - Difficulty level
- The material is saved in your personal storage

### 3. Add learning material

Run command: **/quiz**

Or click action button after adding a new material:

🧠 “Take a quiz on this material”

What happens:

- The bot selects a saved learning item
- Generates 5 multiple-choice questions
- Each question has 4 options (A–D)

### 4. Answer questions

Click one of the buttons:

- A
- B
- C
- D

The bot will:

- Validate your answer
- Show explanation if incorrect
- Track your progress

### 5. Get results

After finishing:

- Total correct answers
- Score percentage
- Final summary of performance
