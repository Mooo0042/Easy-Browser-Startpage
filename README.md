# Browser Start Page

A beautiful, customizable dark mode start page for your web browser with Google search and quick links to your favorite websites.

## Features

- 🔍 **Google Search Bar** - Search directly from your start page
- 🌙 **Dark Mode** - Easy on the eyes with a sleek dark theme
- ⚡ **Auto-Focus Search** - Just start typing to search
- 🖼️ **Favicon Caching** - Loads faster with cached site icons (7-day cache)
- 📶 **Offline Detection** - Warning indicator when internet is down
- 🎨 **Modern Design** - Glassmorphism effects and smooth animations
- ⚙️ **Easy Configuration** - Simple text file for managing links

## Installation

1. Save `startpage.html` to a folder on your computer
2. Set it as your browser's homepage:
   - **Chrome/Edge**: Settings → Appearance → Custom web address
   - **Firefox**: Settings → Home → Custom URLs
   - Or open it manually: `file:///path/to/startpage.html`

## Configuration

Create a file named `links.txt` in the same folder as `startpage.html`.

### Format

Each line should follow this format:

```
URL | Title | Description
```

The description is optional. You can also use:

```
URL | Title
```

### Example `links.txt`

```
https://github.com | GitHub | Code repository and collaboration
https://youtube.com | YouTube | Watch videos and streams
https://reddit.com | Reddit | Social news and discussion
https://mail.google.com | Gmail
https://drive.google.com | Google Drive | Cloud storage
https://netflix.com | Netflix | Streaming service
```

### Rules

- One link per line
- Use the pipe character `|` to separate fields
- URLs must include `https://` or `http://`
- Favicons are automatically fetched
- The instructions box will automatically hide once you have valid links

## Usage Tips

- **Quick Search**: Just start typing anywhere on the page to search Google
- **Updating Links**: Edit `links.txt` and refresh the page

## File Structure

```
my-startpage/
├── startpage.html    # The main start page file
└── links.txt         # Your custom links (create this)
```

## Troubleshooting

**Links not loading?**
- Make sure `links.txt` is in the same folder as `startpage.html`
- Check that each line follows the format: `URL | Title | Description`
- Ensure URLs start with `https://` or `http://`

**"Can't find links.txt" on Linux/local file access?**

Browsers block local file access for security when using `file://` URLs. You **must** use a local web server:

**Solution: Use a Local Web Server**
```bash
# Navigate to your startpage folder:
cd /path/to/your/startpage

# Start a simple web server (Python 3):
python3 -m http.server 8000

# Or if you have Python 2:
python -m SimpleHTTPServer 8000

# Or if you have Node.js installed:
npx http-server -p 8000

# Then open in your browser:
# http://localhost:8000/startpage.html
```

**Set as Homepage:**
Once the server is running, set `http://localhost:8000/startpage.html` as your browser's homepage. You'll need to keep the server running, or add it to your startup scripts.

**Auto-start on Boot (Optional):**
Create a systemd service or add the Python command to your `.bashrc` / startup applications.

**Favicons not showing?**
- Some sites block favicon requests - a fallback globe icon (🌐) will appear

**Search not working?**
- Make sure you have an internet connection
- Check if you can access google.com in your browser

## Customization

The page uses localStorage for caching favicons. Each favicon is stored for 7 days before being refreshed automatically.

Colors and styles can be customized by editing the CSS in the `<style>` section of `startpage.html`.

---

Enjoy your new start page! 🚀