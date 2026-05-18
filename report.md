# Telegram Quiz Bot – Development Report

The schema is stored in this repo: **SelfTeacher_N8N_schema.json**

## Overview

This project is a Telegram-based quiz bot built using **n8n automation platform**.  
The bot allows users to answer multiple-choice questions (A–D), evaluates their responses, tracks progress, and calculates final scores.

The main goal was to build an automated quiz system without traditional backend development, relying instead on workflow automation and integrations.

---

## Tools & Technologies Used

### 1. n8n (Core Platform)

- Used as the main backend orchestration tool
- Handles all logic workflows (quiz flow, validation, scoring)
- Eliminates need for custom server implementation

### 2. Telegram Bot API

- Used for user interaction
- Sends questions and receives answers via messages and callbacks
- Supports HTML formatting for better UX

### 3. JavaScript (n8n Code Nodes)

- Used for:
  - Answer validation
  - Score calculation
  - Question sorting and progression logic
  - Detecting next unanswered question
- Provided flexibility beyond built-in n8n nodes

### 4. Expressions (n8n templating)

- Used for dynamic data binding inside nodes
- Example: `{{ $json.question }}`, `{{ $json.quizId }}`

---

## Features Implemented

- Multiple-choice quiz system (A, B, C, D)
- Automatic answer validation
- Instant feedback with explanations
- Score calculation in percentage
- Sequential question flow (next unanswered question detection)
- Sorting questions by quizId (Q1, Q2, Q3...)
- Final result summary message for users
- Support for both message and callback query inputs

---

## What Worked Well

- **n8n Code Nodes** were extremely effective for implementing custom logic without backend infrastructure
- Telegram integration was fast and reliable for real-time interaction
- Expression system made dynamic message generation simple and flexible
- JSON-based data structure made it easy to manipulate quiz questions
- Workflow-based architecture allowed rapid iteration and debugging

---

## Challenges & What Did Not Work Perfectly

- Handling Telegram `message` vs `callback_query` required careful conditional logic
- Initial issues with extracting nested chat IDs in expressions
- Sorting and sequencing questions required explicit parsing of `quizId`
- Ensuring consistent data structure across nodes was critical to avoid undefined values
- n8n expressions sometimes behave unexpectedly when mixing multiple optional paths

---

## Key Design Decisions

- Chose **n8n over custom backend** to speed up development and reduce complexity
- Used **JavaScript Code nodes** instead of pure visual workflows for logic-heavy parts
- Standardized quiz format:
  - `quizId`
  - `question`
  - `options`
  - `correctAnswer`
  - `userAnswer`
- Stored answers directly in workflow state instead of external database (for simplicity)
- Used sequential question flow instead of randomization for better user experience

---

## Conclusion

This project demonstrates how complex interactive systems like a quiz bot can be built entirely using workflow automation tools such as n8n combined with Telegram API and lightweight JavaScript logic.

The final system is scalable, easy to modify, and does not require traditional backend infrastructure.

Future improvements could include:

- Database integration for persistent user tracking
- Leaderboard system
- Adaptive difficulty levels
- Multi-user analytics dashboard
