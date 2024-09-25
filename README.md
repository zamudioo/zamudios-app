# Zamudios app
## THIS SHI IS FUCKING ASS IM TRYING MY BEST TO DO SMTHING BUT SHIET THIS IS NASTY

This project is a Python-based WhatsApp bot that leverages Selenium to interact with WhatsApp Web. The bot can send and receive messages, perform Google searches based on specific commands, and take screenshots of web pages. The bot also includes a simple GUI for starting detection of incoming messages and saving browser cookies.

## Features

- **Automated WhatsApp messaging**: Send and receive messages on WhatsApp Web.
- **Command-based interactions**: Respond to specific commands (e.g., `#bot busca "query"`) to perform actions such as web searches.
- **Google Search integration**: Perform Google searches directly from WhatsApp and return the top 5 results.
- **Screenshot and text extraction**: Take screenshots of web pages and extract text content to send via WhatsApp.
- **Cookie management**: Save and load session cookies for persistent WhatsApp Web login.
- **Log messages**: Store all received messages in a log file for future reference.
- **Simple GUI**: A graphical interface to manage bot operations.

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/whatsapp-bot.git
    cd whatsapp-bot
    ```

2. **Install dependencies**:
    The project requires Python 3 and the following packages:
    ```bash
    pip install selenium
    pip install tk
    ```

3. **Download WebDriver**:
    - Download the [ChromeDriver](https://chromedriver.chromium.org/downloads) that matches your version of Chrome.
    - Place it in your project directory or add it to your system PATH.

4. **Prepare `whatsapp_cookies.json` (optional)**:
    If you have previously saved cookies, you can place the `whatsapp_cookies.json` file in the project directory to skip the manual login.

## Usage

1. **Run the bot**:
    Start the bot with the following command:
    ```bash
    python bot.py
    ```

2. **Login to WhatsApp Web**:
    - The bot will open WhatsApp Web. If cookies are saved, they will be loaded automatically. Otherwise, you'll need to scan the QR code manually.

3. **Command Syntax**:
    The bot listens for commands in the form of messages starting with `#bot`. Example:
    - **Search Google**: Send `#bot busca "your query"` to perform a Google search. The bot will respond with the top 5 results and allow you to open any link.

4. **Save Cookies**:
    The GUI provides a button to save the current session's cookies, which can be used for future logins.

## Project Structure
```
├── whatsapp_cookies.json # Stores cookies for WhatsApp Web session 
├── mensajes_log.txt # Logs all received messages 
├── captura.png # Screenshot of a webpage (created during usage) 
├── bot.py # Main script containing the bot's functionality 
└── README.md # Project documentation
```

## How It Works

- **Message Handling**:
    - The bot listens for new messages and processes commands that start with `#bot`.
    - Supported commands include Google search (`#bot busca "your query"`).
  
- **Google Search**:
    - The bot opens a new browser tab, performs a Google search, and sends the top 5 results back to WhatsApp.
    - The user can select a result by responding with the corresponding number.

- **Screenshot and Text Extraction**:
    - After selecting a search result, the bot takes a screenshot of the page and extracts the page's text content, sending the first 4000 characters back to WhatsApp.

## GUI Controls

- **Start Detection**: Begin listening for new messages and processing commands.
- **Save Cookies**: Save the current session's cookies for future use.
