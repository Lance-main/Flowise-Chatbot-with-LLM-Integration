# Flowise-Chatbot-with-LLM-Integration

# Movie Review Hub Chatbot

This repository contains the setup and configuration for a local LLM chatbot tailored to handle movie-related queries. The chatbot is created using Ollama Llama 3 and Flowise, and is integrated with a movie review hub website.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
    1. [Update Node.js](#update-nodejs)
    2. [Install Flowise](#install-flowise)
    3. [Configure Ollama](#configure-ollama)
3. [Running the Services](#running-the-services)
4. [Integration with Movie Review Hub Website](#integration-with-movie-review-hub-website)
5. [Usage](#usage)


## Prerequisites

Before starting, ensure you have the following software installed:

- Node.js (version 14 or higher)
- npm (Node Package Manager)
- Git

## Installation

### Update Node.js

First, update Node.js to the latest version:

1. Download and install the latest Node.js from the [official website](https://nodejs.org/).
2. Verify the installation:

   ```sh
   node -v
   npm -v
   ```

### Install Flowise

Follow these steps to install and set up Flowise:

1. **Install Flowise Globally:**
   To install Flowise globally using npm, open your terminal and run the following command:

   ```sh
   npm install -g flowise
   ```

   This command installs Flowise globally on your system, making it available for use in any directory.

2. **Start Flowise:**
   Once Flowise is installed, you can start it using npx. Run the following command in your terminal:

   ```sh
   npx flowise start
   ```

   This command initializes and starts Flowise.

3. **Verification:**
   After running the above commands, Flowise should start, and you should see output indicating that the server is running. Flowise should now be running on port 3000.

### Configure Ollama

Ollama Llama 3 should be running locally on port 11434 as mentioned in the previous repository.

Verify Ollama is running by accessing `http://localhost:11434`.

## Running the Services

To run the chatbot services, follow these steps:

1. Go to the webpage's code folder and run the following command:

   ```sh
   python -m http.server 9000
   ```

   This will host the webpage (which has the chatbot embedded) locally on port 9000.

## Integration with Movie Review Hub Website

To integrate the chatbot with the movie review hub website:

1. Modify the frontend code of  movie review hub to include a chatbot interface (e.g., a chat window or button).
2. Set up communication between the frontend and Flowise backend (running on port 3000) to handle user queries.
3. Ensure the chatbot only handles movie-related queries by configuring the Flowise workflow.

The following HTML code was embedded in the `index.html` to add the chatbot:

```html
<script type="module">
    import Chatbot from "https://cdn.jsdelivr.net/npm/flowise-embed/dist/web.js"
    Chatbot.init({
        chatflowid: "f23ed3b3-d8f5-4d40-92e5-9b250ce15e5f",
        apiHost: "http://localhost:3000",
    })
</script>
```

## Usage

Once everything is set up:

1. Access  movie review hub website at `http://localhost:9000`.
2. Interact with the chatbot through the chatbot icon added.

The chatbot will handle movie-related queries and provide responses accordingly.

