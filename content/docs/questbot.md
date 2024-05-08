---
title: "QuestBot"
weight: 5
draft: false
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
bookSearchExclude: false
---

# QuestBot Technical Documentation
![QuestBot Image](/questbot.png)

QuestBot is an AI-powered chatbot designed to assist students by providing instant answers to questions they may have during lessons. This documentation outlines the technical implementation of QuestBot, focusing on its integration with the ChatGPT API, frontend interactions, and backend data handling.

## System Overview

QuestBot utilizes OpenAI's ChatGPT API to generate responses based on natural language input from users. The system architecture is designed to ensure smooth interaction between the user interface on the frontend and the AI processing on the backend.

## Frontend Integration

### User Interface

- **Chat Interface**: The frontend features a chat interface where users can input their questions. This interface is built using ReactJS to manage real-time user interactions efficiently.
- **Session Management**: User sessions are managed through local storage to maintain context between page reloads, ensuring a seamless user experience during an active chat session.

### Request Handling

- **API Calls**: JavaScript fetch API is used for asynchronous requests to the backend, which handles the communication with the ChatGPT API.
- **Input Validation**: User inputs are validated on the frontend to ensure that queries are in a suitable format before being sent to the backend.

## Backend Integration

### API Communication

- **Endpoint Configuration**: The backend, developed with Node.js and Express, is configured to route requests to the OpenAI API endpoint.
- **API Key Management**: API keys are stored securely using environment variables and are loaded through server-side configuration to maintain security.

### Data Processing

- **Request Formatting**: Incoming requests from the frontend are formatted to adhere to the ChatGPT API's expected JSON structure.
- **Response Handling**: The backend parses the ChatGPT API's response and formats it into a user-friendly format before sending it back to the frontend.

## Security Measures

- **Data Encryption**: All data transmitted between the frontend and backend is encrypted using SSL/TLS.
- **API Security**: Access to the ChatGPT API is secured with authentication mechanisms to prevent unauthorized use.

## Example Code Snippet

Below is an example of how a request to the ChatGPT API is handled by the backend:

```javascript
const express = require('express');
const fetch = require('node-fetch');
const app = express();
app.use(express.json());

const API_URL = 'https://api.openai.com/v1/chat/completions';
const API_KEY = process.env.OPENAI_API_KEY;

app.post('/query', async (req, res) => {
    const userMessage = req.body.message;
    try {
        const response = await fetch(API_URL, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': `Bearer ${API_KEY}`
            },
            body: JSON.stringify({
                model: "gpt-3.5-turbo",
                prompt: userMessage,
                max_tokens: 150
            })
        });
        const data = await response.json();
        res.send({ message: data.choices[0].text.trim() });
    } catch (error) {
        res.status(500).send({ error: 'Failed to fetch response from OpenAI.' });
    }
});
```