# AI ChatBot Project  

## Project Overview  

This project implements an **AI ChatBot** that interacts with chat history, analyzes conversations, and generates witty or contextually relevant responses using **OpenAI's GPT-3.5-Turbo** model. The bot mimics a humorous and friendly persona who speaks both **Hindi** and **English** and has a coder's perspective. It automates the chat response process using **PyAutoGUI** to control screen actions, such as copying chat history and pasting responses.

---

## Features  

1. **Chat Analysis and Response**  
   - The bot analyzes the chat history and generates the next appropriate message.  

2. **Funny Roasts**  
   - Designed to humorously "roast" participants in the conversation while staying context-aware.  

3. **Language Support**  
   - Supports both **Hindi** and **English** for multilingual interactions.

4. **Automation Using PyAutoGUI**  
   - Simulates human-like actions to copy, paste, and send messages.  

5. **OpenAI Integration**  
   - Utilizes **OpenAI GPT-3.5-Turbo** to generate intelligent and context-aware responses.  

6. **Coordinate Helper**  
   - The `cursor.py` script helps find exact mouse coordinates for automated tasks.  

---

## Table of Contents  

1. [Installation](#installation)  
2. [Project Structure](#project-structure)  
3. [Dependencies](#dependencies)  
4. [How It Works](#how-it-works)  
5. [Usage](#usage)  
6. [Customization](#customization)  
7. [Limitations](#limitations)  
8. [Future Improvements](#future-improvements)  

---

## Installation  

Follow these steps to set up and run the project:

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/your-username/ai-chatbot.git
   cd ai-chatbot
   ```

2. **Install Required Libraries**  
   Use `pip` to install the necessary Python libraries:  
   ```bash
   pip install pyautogui pyperclip openai
   ```

3. **Set Up OpenAI API Key**  
   - Get your OpenAI API key from [OpenAI's platform](https://platform.openai.com/).  
   - Replace `<Your Key Here>` in `bot.py` and `open_ai.py` with your API key:  
     ```python
     client = OpenAI(api_key="<Your Key Here>")
     ```

4. **Run the Scripts**  

   - **Coordinate Finder**: Use `cursor.py` to identify screen coordinates.  
     ```bash
     python cursor.py
     ```
   - **ChatBot Automation**: Run the bot script to automate chats:  
     ```bash
     python bot.py
     ```

   - **Test OpenAI Interaction**: Test the chatbot's response generation with `open_ai.py`.  
     ```bash
     python open_ai.py
     ```

---

## Project Structure  

```bash
├── bot.py          # Main script for automating chats and generating responses
├── cursor.py       # Script to determine mouse coordinates
├── open_ai.py      # OpenAI interaction test script
└── README.md       # Project documentation
```

---

## Dependencies  

| Library            | Description                                       |
|--------------------|---------------------------------------------------|
| `pyautogui`        | Simulates keyboard and mouse actions.             |
| `pyperclip`        | Handles copying and pasting data to/from clipboard.|
| `openai`           | Provides API access to OpenAI's GPT models.       |
| `time`             | Adds delays for better automation.                |

Install all dependencies using:  
```bash
pip install pyautogui pyperclip openai
```

---

## How It Works  

1. **Automated Screen Actions**  
   - Using `PyAutoGUI`, the script performs the following tasks:  
     - Selects and copies the chat history by simulating mouse dragging.  
     - Pastes the AI-generated response and sends it via simulated keyboard input.

2. **Chat Analysis**  
   - The function `is_last_message_from_sender()` checks if the last message in the chat history is sent by a specific user (e.g., **"Rohan Das"**).  

3. **AI Response Generation**  
   - The script sends the chat history to OpenAI's GPT-3.5-Turbo model, along with instructions to analyze and respond like a coder named **Naruto** who uses both Hindi and English.  

4. **Response Sending**  
   - The generated response is copied to the clipboard and pasted into the chat input box.  

---

## Usage  

### 1. Find Mouse Coordinates  
Run the `cursor.py` script to find screen coordinates for:  
- Chat selection  
- Input box  
- Send button  

```bash
python cursor.py
```

Hover the mouse over the target area to get real-time coordinates.

---

### 2. Run the ChatBot Automation  
Run the `bot.py` script to start the automation:  
```bash
python bot.py
```

The script will:  
- Copy chat history.  
- Check the last sender's message.  
- Generate a humorous AI response.  
- Paste and send the response.  

---

### 3. Test AI Interaction  
Run `open_ai.py` to test OpenAI's responses with hardcoded chat history:  
```bash
python open_ai.py
```

---

## Customization  

1. **Change Sender's Name**  
   Update the `sender_name` parameter in `is_last_message_from_sender()` to monitor messages from a specific user:  
   ```python
   if is_last_message_from_sender(chat_history, sender_name="Your Friend's Name"):
   ```

2. **Change AI Persona**  
   Modify the system instructions in the API call to adjust the bot's personality:  
   ```python
   {"role": "system", "content": "You are a coder who loves roasting people in Hindi."}
   ```

3. **Adjust Coordinates**  
   Use `cursor.py` to reconfigure mouse click and drag coordinates in `bot.py`.

---

## Limitations  

1. **Screen Resolution Dependent**  
   - Mouse coordinates must match your screen resolution and chat application's UI.

2. **HTML-Based Chats**  
   - If chat history isn't copyable via **Ctrl+C**, this approach will not work.

3. **Rate Limiting**  
   - OpenAI has API rate limits, so excessive requests may lead to temporary blocks.

4. **Dynamic Elements**  
   - UI changes in chat applications may require updates to the coordinates.

---

## Future Improvements  

- **Add Pagination**: Handle larger chat histories.  
- **UI Independence**: Integrate OCR or APIs for dynamic chat selection.  
- **Enhanced AI Instructions**: Add personas for diverse use cases (formal, sarcastic, poetic).  
- **Error Handling**: Robust error handling for UI delays or unexpected changes.  

---

### Acknowledgments  

- **OpenAI** for providing GPT-3.5-Turbo API.  
- **PyAutoGUI** for automating mouse and keyboard actions.  

---

### Happy Coding and Chat Roasting! 😎🔥  
