# Finite State Machine Designer

An interactive HTML5 canvas-based tool for designing and visualizing finite state machines.

Original: http://madebyevan.com/fsm/

## Features

### Core Functionality

- **Add states**: Double-click on the canvas to create new states
- **Add transitions**: Shift-drag between states to create directed arrows
- **Move elements**: Drag states and arrows to reposition them
- **Delete elements**: Select an element and press Delete key
- **Accept states**: Double-click on an existing state to toggle accept state (double circle)

### Enhanced Features

- **Undo/Redo**: Full history tracking with Ctrl+Z (undo) and Ctrl+Y (redo)
- **Clear All**: One-click button to reset the entire canvas (can be undone)
- **Bidirectional arrows**: When two states connect both ways, the second arrow automatically curves to stay distinct
- **Large canvas**: 1800x1000px responsive canvas that scales to fit your screen
- **Auto-save**: Your work is automatically saved to browser localStorage

### Text Formatting

- **Numeric subscripts**: Use underscore notation (e.g., `S_0` → S₀)
- **Greek letters**: Use backslash notation (e.g., `\alpha` → α, `\beta` → β)

### Export Options

- **PNG**: Download as high-quality image
- **SVG**: Export as scalable vector graphics
- **LaTeX**: Generate LaTeX code for academic papers

## How to Run Locally

### Prerequisites

- Python 2.x or 3.x (for building)
- Modern web browser with HTML5 canvas support

### Setup Instructions

1. **Clone or download this repository**

2. **Build the project**

   The JavaScript source files need to be combined into a single file:

   ```bash
   python build.py
   ```

   This creates `www/fsm.js` from all files in the `src/` directory.

   _Optional:_ Use watch mode for automatic rebuilding during development:

   ```bash
   python build.py --watch
   ```

3. **Open in browser**

   **Option A** - Direct file access:
   - Simply open `www/index.html` in your web browser

   **Option B** - Local server (recommended):

   ```bash
   cd www
   # Python 3
   python -m http.server
   # Python 2
   python -m SimpleHTTPServer
   ```

   Then navigate to `http://localhost:8000`

## Keyboard Shortcuts

- **Ctrl+Z** / **Cmd+Z**: Undo last action
- **Ctrl+Y** / **Cmd+Y**: Redo undone action
- **Delete**: Remove selected element
- **Shift+Drag**: Create new transition arrow

## Project Structure

```
fsm/
├── src/
│   ├── elements/        # Node and link classes
│   ├── export_as/       # Export functionality (SVG, LaTeX)
│   └── main/            # Core FSM logic and UI
├── www/
│   ├── index.html       # Main HTML page
│   └── fsm.js           # Built JavaScript (generated)
├── build.py             # Build script
└── README.md
```

## Technical Details

- Built with vanilla JavaScript and HTML5 Canvas
- No external dependencies
- Responsive design with max-width constraints
- LocalStorage persistence for auto-saving
- Up to 50 undo/redo history states

## Credits

Created by [Evan Wallace](http://madebyevan.com/) in 2010

Enhanced with additional features including undo/redo, bidirectional arrow handling, and improved canvas sizing.
