# Songs List Manager

A Flask-based web application for managing your song practice list. Track songs you're learning, monitor your proficiency level, log practice sessions, and maintain notes about each song.

## Features

- 📝 **Song Management**: Add, edit, and delete songs with artist and title information
- ⭐ **Proficiency Tracking**: Click on stars to rate your skill level (0-5 stars) for each song
- 🔗 **Auto-Generated Links**: Automatically creates search links for:
  - YouTube (song search)
  - Google (lyrics search)
  - Ultimate Guitar (chords/tabs search)
- 📅 **Practice Logging**: Track when you last played each song
- 📓 **Notes**: Click on any song title or artist to add/edit practice notes
- 🔍 **Search**: Quickly find songs by artist or title
- 📱 **Mobile Responsive**: Optimized for both desktop and mobile devices
- 🎨 **Modern UI**: Clean interface with gradient design and smooth animations

## Requirements

- Python 3.12+
- MySQL database
- Flask web framework

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd songs-list
   ```

2. **Create and activate virtual environment**
   ```bash
   python3 -m venv flask_env
   source flask_env/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up MySQL database**
   ```bash
   mysql -u root -p < setup_database.sql
   ```

5. **Configure database connection**
   - Copy `config_template.py` to `config.py`
   - Update the database credentials in `config.py`:
     ```python
     DB_CONFIG = {
         'host': 'localhost',
         'user': 'your_username',
         'password': 'your_password',
         'database': 'songs_list_db'
     }
     ```

6. **Run the application**
   ```bash
   python app.py
   ```

7. **Access the app**
   - Open your browser to `http://localhost:5000`

## Usage

### Adding a Song
1. Click the **"+ Add Song"** button
2. Enter the artist name and song title
3. Select initial proficiency level (optional)
4. Click **"Add Song"**
5. Links to YouTube, lyrics, and chords are automatically generated

### Managing Proficiency
- Click on any star (1-5) in the proficiency column to update your skill level
- Stars fill from left to right

### Logging Practice
- Click **"Log Play"** to record that you practiced the song today
- The "Last Played" date will update automatically

### Adding/Editing Notes
- Click on any **song title** or **artist name** to open the notes modal
- Enter practice tips, chord progressions, difficulty notes, etc.
- Click **"Save Notes"** to save

### Editing Song Details
- Click **"Edit"** to modify artist, title, proficiency, or any of the links
- Click **"Update Song"** to save changes

### Deleting Songs
- Click **"Delete"** and confirm to remove a song from your list

### Searching
- Use the search box at the top to filter songs by artist or title
- Search works in real-time

## Database Schema

The application uses a single `songs` table with the following structure:
- `id`: Auto-incrementing primary key
- `artist`: Artist/band name
- `title`: Song title
- `proficiency`: Star rating (☆☆☆☆☆ to ★★★★★)
- `link`: YouTube search URL
- `lyrics_link`: Google lyrics search URL
- `chords_link`: Ultimate Guitar search URL
- `notes`: Freeform text notes
- `last_played`: Date of last practice session
- `created_at`: Record creation timestamp
- `updated_at`: Last update timestamp

## Technology Stack

- **Backend**: Flask 3.0.0
- **Database**: MySQL 8.0+ with mysql-connector-python
- **Frontend**: HTML5, CSS3, JavaScript (vanilla)
- **Templating**: Jinja2
- **Environment**: Python virtual environment (venv)
