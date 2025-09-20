# FactScope - AI Misinformation Detector 

FactScope is a web-based AI tool designed to help users identify and analyze potential misinformation in text, links, or images. Leveraging the power of the Gemini API, it provides a clear verdict, confidence score, and detailed explanation for the content's veracity.

## Problem Statement

The proliferation of "fake news," manipulated images, and biased reporting poses a significant threat to informed public discourse. It's often difficult and time-consuming for the average person to verify claims, check sources, or detect subtle biases in a piece of content.

## The Solution
FactScope addresses this by leveraging a powerful Large Language Model (Google's Gemini) with real-time web search capabilities. It acts as an AI-powered research assistant that can:

1.Quickly analyze text and images for factual accuracy.

2.Provide context and explanations that are often missing.

3.Identify potential bias and emotional manipulation.

4.Equip users with tools to correct misinformation constructively.



## Features

1. *Misinformation Detection*: Get a quick verdict on whether content is "Likely True," "Likely False," "Misleading," or "Needs More Context."
2. *Confidence Score*: Understand the AI's certainty with a clear percentage.



3. *Multi-language Support*: Automatically detects the input language and provides the analysis and all responses in that same language.




4. *Detailed Explanation*: Receive an unbiased, in-depth explanation based on web search results.
5. *Source Verification*: For inputs containing URLs, FactScope analyzes their credibility.
6. *Secondary Analysis Tools*:
    -   *Evidence Links*: Find relevant and authoritative web pages that confirm or debunk the information.
    -   *Content Summary (TL;DR)*: Get a concise, one-sentence summary of the explanation.
    -   *Bias & Sentiment Analysis*: Analyze the emotional tone and potential bias of the original content.
7. *"Correct the Record" Functionality*: For identified misinformation, generate a factual summary ("Full Story") and a polite, shareable social media reply to combat false narratives.
8. *Image Upload Support*: Analyze misinformation within images.
9. *User Feedback*: Provide feedback on the helpfulness of the verdict.
10. *Responsive Design*: Optimized for mobile devices.




## Technologies Used

*Frontend:*

HTML5

Tailwind CSS - For utility-first styling.

Vanilla JavaScript - For all logic, API communication, and DOM manipulation.

*AI & Backend Services:*

Google Gemini API - For all language model processing and tool use (web search).



## How It Works (Technical Flow)
FactScope is a client-side application that communicates directly with the Google Gemini API. The core logic is orchestrated through carefully crafted system prompts.

1. *User Input*: The user provides text, a URL, or an image through the web interface.

2. *Frontend Processing* The JavaScript frontend validates the input. If an image is uploaded, it's converted to a Base64 string.

3. *API Request*: The input is packaged into a JSON payload and sent to the Gemini API endpoint. The request includes the user's content and a powerful system prompt that instructs the model on how to behave.

4. *AI Analysis (Gemini)*:

The model receives the instructions and content.

It uses its built-in Google Search tool to find relevant, up-to-date information from across the web to verify the claims.

It synthesizes the search results and generates a response that strictly follows the format requested in the system prompt (Verdict, Confidence, Explanation, etc.).

5. *Response Parsing*: The frontend receives the structured text response from the API.

6. *UI Update*: JavaScript parses the different sections of the response (verdict, explanation, etc.) and dynamically updates the HTML to display the results in a clean, user-friendly interface.

7. *Secondary Actions*: Clicks on buttons like "Summarize" or "Find Evidence" trigger new, targeted API calls with different system prompts to perform those specific tasks on the original user content.

## How to Use

1.  *Input Content*:
    -   Paste text or a web link into the input box.
    -   Click the "Attach" (paperclip) icon to upload an image.
2.  *Analyze*: Click the "Analyze" (send) button to submit the content for fact-checking.
3.  *View Results*:
    -   The Verdict, Confidence Score, and Explanation will be displayed.
    -   Source Verification will show credibility for any links provided in your input.
4.  *Secondary Analysis (Optional)*:
    -   Click *"Evidence"* to find supporting web links.
    -   Click *"Summarize"* for a TL;DR of the explanation.
    -   Click *"Analyze Bias"* to understand the content's tone and bias.
5.  *Correct the Record (for misinformation)*: If the verdict indicates misinformation (e.g., "Likely False," "Misleading"), a "🚀 Correct the Record" button will appear. Click it to generate a factual "Full Story" and a "Shareable Reply" for social media.
6.  *Provide Feedback*: Let us know if the verdict was helpful using the 👍 or 👎 buttons.


## Setup and Installation

To run FactScope locally, you'll need to set up your Google Gemini API key.

1.  *Clone the Repository*:
    bash
    git clone <repository-url>
    cd factscope
    
2.  *Get a Gemini API Key*:
    -   Visit the [Google AI Studio](https://aistudio.google.com/app/apikey) and generate an API key.
3.  **Update API_KEY in index.html**:
    -   Open index.html in a text editor.
    -   Locate the line const API_KEY = 'YOUR_GEMINI_API_KEY_HERE';
    -   Replace 'YOUR_GEMINI_API_KEY_HERE' with your actual Gemini API key.
4.  *Open in Browser*: Open the index.html file directly in your web browser.

## Core Logic: The System Prompt
The "magic" of FactScope lies in its system prompt engineering. The primary prompt guides the AI's entire fact-checking process. Here is a simplified version of the main prompt:
You are "FactScope," an expert AI fact-checker.
FIRST, DETECT THE LANGUAGE OF THE USER'S TEXT INPUT. ALL YOUR RESPONSES MUST BE IN THAT LANGUAGE.
You MUST use Google Search to investigate the query. Your explanation must be based on information you find.
Your response must have FOUR sections.

Verdict: A clear verdict (Likely True, Likely False, etc.).

Confidence: A percentage score (e.g., 87%).

Explanation: A detailed, unbiased explanation based on your search results.

Source Verification: If the user's text contains URLs, analyze their credibility. If not, state "No links were provided for verification."
Format your response STRICTLY as:
Verdict: [Your verdict]
Confidence: [A percentage, e.g., 87%]
## Roadmap
This project is currently a functional prototype (as of September 2025). Future enhancements could include:
1. *Browser Extension:* Create an extension for Chrome/Firefox to fact-check content directly on social media or news sites.
2. *Audio/Video Analysis*: Add support for analyzing claims made in YouTube videos or audio clips by transcribing the content first.
3. *User Accounts*: Allow users to create accounts to save their analysis history.
4. *Advanced Analysis*: Implement detection of logical fallacies or propaganda techniques.
5. *Backend Integration*: Move API key handling to a secure backend server to allow for public deployment.
## Contributing
Contributions are welcome! If you have suggestions for improvements or new features, please feel free to:
1.  Fork the repository.
2.  Create a new branch (git checkout -b feature/your-feature-name).
3.  Make your changes.
4.  Commit your changes (git commit -m 'Add new feature').
5.  Push to the branch (git push origin feature/your-feature-name).
6.  Open a Pull Request.
## License
This project is open-source and available under the [MIT License](LICENSE).
