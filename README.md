# JSON Editor - MR901.CO.IN

A powerful, feature-rich JSON editor ready for GitHub Pages deployment. Edit, validate, format, and transform JSON with ease.

![JSON Editor](https://img.shields.io/badge/JSON-Editor-667eea?style=for-the-badge)
![License](https://img.shields.io/badge/License-Apache%202.0-blue?style=for-the-badge)

## 🚀 Features

### Core Editing Features
- **Multiple Modes**: Switch between Tree, Code, and Text editing modes
- **Drag & Drop**: Reorder items easily in tree view
- **Search & Replace**: Find and replace text with Ctrl+F / Ctrl+H
- **Undo/Redo**: Full undo/redo support (Ctrl+Z / Ctrl+Y)

### Advanced Features
- **JSON Schema Validation**: Automatic validation with visual error indicators
- **Color Picker**: Click on hex color values to open built-in color picker
- **Repair JSON**: Automatically fix common JSON syntax errors
- **Format/Compact**: Pretty-print or minify JSON with one click

### File Operations
- **Load JSON**: Import JSON files from your computer
- **Save JSON**: Export JSON to local files
- **Example Data**: Quick-start with example JSON

## 🎯 Usage

### Online
Simply open `index.html` in your web browser or visit the deployed GitHub Pages URL.

### Local Development
1. Clone this repository
2. Open `index.html` in your browser
   - Or run a local server: `python3 -m http.server 8888`
   - Access at: `http://localhost:8888`

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+Z` | Undo |
| `Ctrl+Y` or `Ctrl+Shift+Z` | Redo |
| `Ctrl+F` | Search |
| `Ctrl+H` | Search & Replace |
| `Ctrl+D` | Duplicate field/value |
| `Ctrl+Enter` | Open link or color picker |
| `Alt+End` | Move to last field |
| `Ctrl+M` | Show actions menu |

## 🌐 GitHub Pages Deployment

### Method 1: Direct Deployment
1. Push this directory to your GitHub repository
2. Go to repository Settings → Pages
3. Set source to main branch → `/jsoneditor` folder
4. Your editor will be live at `https://yourusername.github.io/repository/jsoneditor/`

### Method 2: Root Deployment
1. Move all files from `jsoneditor/` to repository root
2. Go to repository Settings → Pages
3. Set source to main branch → root
4. Your editor will be live at `https://yourusername.github.io/repository/`

## 📁 File Structure

```
jsoneditor/
├── index.html              # Main application file
├── dist/                   # Distribution files
│   ├── jsoneditor.min.js   # Minified JavaScript
│   ├── jsoneditor.min.css  # Minified CSS
│   └── img/                # Icons and images
├── docs/                   # API documentation
├── README.md               # This file
├── LICENSE                 # Apache 2.0 License
└── NOTICE                  # Copyright notices
```

## 🎨 Customization

You can customize the editor by modifying `index.html`:

### Change Colors
Edit the CSS gradient in the `<style>` section:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

### Add JSON Schema Validation
Add schema to editor options:
```javascript
const options = {
  schema: {
    type: 'object',
    properties: {
      name: { type: 'string' },
      age: { type: 'number' }
    }
  }
};
```

### Change Default Example
Modify the `loadExample()` function in the script section.

## 🛠️ Technologies

- **JSONEditor**: [josdejong/jsoneditor](https://github.com/josdejong/jsoneditor) - Core editor library
- **FileSaver.js**: File download functionality
- **Vanilla JavaScript**: No framework dependencies
- **Modern CSS**: Responsive design with CSS Grid and Flexbox

## 📝 License

This project uses JSONEditor which is licensed under the Apache 2.0 License.

Original JSONEditor by Jos de Jong: https://github.com/josdejong/jsoneditor

## 🤝 Credits

- **JSONEditor Library**: [Jos de Jong](https://github.com/josdejong)
- **Custom Implementation**: [MR901.CO.IN](https://mr901.co.in)

## 📧 Support

For issues related to:
- **This implementation**: Contact via [MR901.CO.IN](https://mr901.co.in)
- **JSONEditor library**: See [JSONEditor GitHub](https://github.com/josdejong/jsoneditor/issues)

## 🌟 Features Showcase

### Tree Mode
- Visual hierarchical view
- Expandable/collapsible nodes
- Drag-and-drop reordering
- Context menu for actions
- Color picker for hex values

### Code Mode
- Syntax highlighting (powered by Ace)
- Line numbers
- Code folding
- Auto-completion
- Error detection

### Text Mode
- Plain text editing
- Fast for large files
- Simple copy/paste
- Minimal interface

---

Made with ❤️ by [MR901.CO.IN](https://mr901.co.in)
