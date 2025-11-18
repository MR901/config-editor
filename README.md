# Config Editor

A powerful JSON/YAML editor for editing configuration files. Features a clean interface with multiple editing modes, real-time validation, and bidirectional format conversion.

## Features

### Dual Format Support
- **JSON & YAML**: Seamlessly edit both formats with automatic conversion
- **Format Detection**: Automatically detects file format on load
- **Live Sync**: Real-time synchronization between JSON and YAML views

### Editing Modes
- **Tree Mode**: Visual hierarchical view with drag-and-drop
- **Code Mode**: Side-by-side JSON and YAML editors with syntax highlighting
- **Text Mode**: Simple plain text editing

### Core Functions
- **Load/Save**: Import and export JSON or YAML files
- **Format**: Pretty-print with proper indentation
- **Compact**: Minify to single line
- **Validate**: Real-time syntax and schema validation
- **Repair**: Automatically fix common syntax errors
- **Search**: Find and replace with Ctrl+F / Ctrl+H

## Quick Start

### Local Development

1. **Start a local server**:
   ```bash
   cd config-editor
   python3 -m http.server 8080
   ```

2. **Open in browser**:
   ```
   http://localhost:8080
   ```

### Alternative: Direct Open

Simply open `index.html` directly in your web browser. All features work without a server.

## Usage

### Loading Files

1. Click **↑ Load** button
2. Select a `.json`, `.yaml`, or `.yml` file
3. Format is automatically detected
4. Edit using your preferred mode

### Switching Formats

- Use the **JSON/YAML** toggle buttons in the toolbar
- Save in either format regardless of source format
- Current format is shown in the format badge

### Editing Modes

Switch between modes using the editor's mode selector:

- **Tree**: Best for structural changes and visual editing
- **Code**: Shows both JSON and YAML side-by-side
- **Text**: Simple text editing with live conversion

### Saving Files

1. Make your edits
2. Click **↓ Save** button
3. Choose format (JSON or YAML)
4. Specify filename and location

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `Ctrl+F` | Search |
| `Ctrl+H` | Find & Replace |
| `Ctrl+D` | Duplicate |
| `Ctrl+M` | Actions menu |

## YAML Limitations

Due to JSON-based internal representation, some YAML features are not preserved:

- Comments are not retained
- Anchors and aliases are expanded
- Multi-line string formatting is simplified
- Only the first document in multi-document files is loaded

For best results with YAML, use Tree mode for structural editing.

## GitHub Pages Deployment

### Option 1: Root Deployment

1. Push all files to your repository root
2. Go to repository **Settings** → **Pages**
3. Set source to `main` branch and `/` (root)
4. Your editor will be live at `https://username.github.io/repository/`

### Option 2: Subdirectory Deployment

1. Keep files in `config-editor/` directory
2. Push to repository
3. Go to **Settings** → **Pages**
4. Set source to `main` branch and `/` (root)
5. Access at `https://username.github.io/repository/config-editor/`

### Option 3: Custom Domain

1. Deploy using Option 1 or 2
2. Add a `CNAME` file with your domain name
3. Configure DNS with a CNAME record pointing to `username.github.io`
4. Enable custom domain in repository settings

## File Structure

```
config-editor/
├── index.html              # Main application
├── dist/                   # Production assets
│   ├── jsoneditor.min.js   # Minified JavaScript
│   ├── jsoneditor.min.css  # Minified CSS
│   └── img/                # Icons
├── LICENSE                 # Apache 2.0
├── NOTICE                  # Copyright notices
└── README.md               # This file
```

## Browser Compatibility

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Development

The editor is a single-page application with no build process required. To modify:

1. Edit `index.html` for UI and functionality changes
2. Test locally with a web server
3. Deploy changes by committing and pushing

### Customization

Edit the CSS variables in `index.html` to customize colors:

```css
:root {
  --primary-blue: #2563eb;
  --success-green: #10b981;
  /* ... more variables */
}
```

## Troubleshooting

### Editor Not Loading

- Ensure all files in `dist/` are present
- Check browser console for errors
- Verify paths are relative (not absolute)

### Features Not Working

- Make sure JavaScript is enabled
- Check that CDN resources are accessible
- Clear browser cache and reload

### YAML Not Converting

- Verify YAML syntax is valid
- Check sync status indicators
- Try switching modes (Tree → Code)

## API Usage

For programmatic usage, the editor can be initialized with options:

```javascript
const editor = new JSONEditor(container, {
  mode: 'tree',
  modes: ['tree', 'code', 'text'],
  schema: { /* your JSON schema */ }
});
```

Refer to the inline help panel (? button) for more details.
