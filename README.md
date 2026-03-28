ChatPanel.jsx
    Main chat system (core logic)
    Takes user input and sends to AI
    Receives AI response and updates UI
    Sends canvas shapes + history to backend
    Handles file upload (image/pdf)
MessageBubble.jsx
    Displays each chat message
    Handles user vs AI message UI
    Renders AI response (text + resources)
    Uses structured response (type, message, resources)
    No API logic
ResourceCard.jsx
    Displays resource links (YouTube/article)
    Shows title + clickable link
    Button to send resource to canvas
    Uses resource {kind, title, url}
    Pure UI
services/gemini.js
    Handles AI calls (main API layer)
    Sends message + history + canvas context
    Builds prompt for AI
    Returns structured JSON response
    Will be replaced by FastAPI
storage.js
    Stores chat history in browser
    Uses localStorage
    Save, get, delete chat per page
    Not shared across users
    Temporary (replace with backend later)
HistoryItem.jsx
    Shows one chat session in sidebar
    Displays topic + time
    Handles click (switch session)
    Handles delete session
    Uses session {id, topic, createdAt}
HistoryPanel.jsx
    Stores and displays session history by fetching sessions using getHistory() and grouping them (Today, Yesterday, etc.)

    Creates a new canvas/session using editor.createPage() and saves it with saveSession()

    Handles switching between sessions by loading the correct canvas when a user selects a history item

    Deletes sessions by removing them from both the UI history and the canvas editor

    Controls UI behavior like collapsing/expanding the sidebar and showing an empty state when no history exists