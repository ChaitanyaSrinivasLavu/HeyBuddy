# HeyBuddy Chatbot

## Overview

HeyBuddy is a Flask-based chatbot application designed to assist users in finding information about GITAM University. It uses the Azure OpenAI API to provide intelligent responses to user queries and maintains a history of conversations in a SQLite database.

## Features

- **User Authentication**: Simple login system for admin access.
- **Chatbot Interface**: Users can ask questions and get automated responses.
- **Admin Panel**: Admin can view unresolved chats and manage queries.
- **Conversation History**: Saves chat history in a SQLite database.
- **Azure OpenAI Integration**: Leverages OpenAI's language models to generate responses.

## Setup

### Prerequisites

- Python 3.8 or higher
- Required Python packages: `Flask`, `sqlite3`, `openai`, `gptapi`

### Installation

1. **Clone the repository**:
   ```sh
   git clone https://github.com/your-repo/heybuddy.git
   cd heybuddy
   ```

2. **Install dependencies**:
   ```sh
   pip install Flask sqlite3 openai gptapi
   ```

3. **Set up environment variables**:
   Ensure you have your Azure OpenAI API key and endpoint information available.

### Database Initialization

Initialize the SQLite database by running:
```sh
python -c 'from app import init_sqlite_db; init_sqlite_db()'
```

## Running the Application

Start the Flask app by running:
```sh
python app.py
```

Open your browser and navigate to `http://localhost:5000` to access the application.

## Usage

### User Authentication

1. **Login**:
   - Navigate to `/login/`.
   - Use `admin` as both the username and password to log in.

2. **Admin Panel**:
   - After logging in, you will be redirected to the admin panel where you can view unresolved chats.

### Chatbot Interface

1. **Start a Chat**:
   - Navigate to `/chatbot/`.
   - Enter your name and email to start a chat session.

2. **Chat**:
   - Ask questions and receive responses from the chatbot.
   - If the chatbot cannot resolve your query, it will be marked as unresolved and forwarded to an admin.

### Admin Actions

1. **View Unresolved Chats**:
   - Logged in admins can view all unresolved chats in the admin panel.

2. **Logout**:
   - Admins can log out by navigating to `/logout/`.

## Functions

### `init_sqlite_db()`
Initializes the SQLite database and creates the `chat_history` table if it does not exist.

### `login()`
Handles user login for admin access.

### `admin()`
Displays the admin panel with unresolved chat queries.

### `logout()`
Logs out the current admin user.

### `chat()`
Handles the initial user setup for the chat session.

### `chat_interface()`
Manages the chat interface, processing user queries and responses.

### `get_llm_response(user_query)`
Generates a response from the Azure OpenAI API based on the user's query.

### `save_chat_history(name, email, messages, response_text, status)`
Saves the chat history to the SQLite database.

## Dependencies

- `Flask`: For creating the web application.
- `sqlite3`: For database operations.
- `openai`: For integrating with Azure OpenAI API.
- `gptapi`: For API and endpoint configuration.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

## Acknowledgements

Special thanks to the developers and contributors of the libraries used in this project. Your tools and resources make projects like this possible.

---

Feel free to reach out if you have any questions or need further assistance. Happy chatting with HeyBuddy!
