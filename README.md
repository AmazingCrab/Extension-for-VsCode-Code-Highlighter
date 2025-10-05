# Code Highlighter

<div align="center">

[![VS Code Marketplace](https://img.shields.io/badge/VS%20Code-Marketplace-blue?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support%20Me-FF5E5B?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/amazingcrab)

**A powerful Visual Studio Code extension for marking and organizing your code with customizable colors.**

Perfect for architecture planning, module identification, and visual code organization.

[Features](#-features) • [Installation](#-getting-started) • [Usage](#-customization) • [Support](#-support-the-project)

</div>

---

## 🎥 Demo

<div align="center">
  <a href="https://www.youtube.com/watch?v=exmPVToYdi4">
    <img src="https://img.youtube.com/vi/exmPVToYdi4/maxresdefault.jpg" alt="Code Highlighter Demo">
    <br>
    <img src="https://img.shields.io/badge/▶_WATCH_DEMO-FF0000?style=for-the-badge&logoColor=white" alt="Play Button">
  </a>
  
  *Click to watch the demo video*
</div>

---

## ✨ Features

### 🎨 Architecture-Focused Color Coding
- **10 predefined architectural layers** with meaningful names and descriptions
- Default colors include: Model Layer, View Layer, Controller Layer, Service Layer, Data Access, API Routes, Utilities, Configuration, Authentication, and Testing
- **Fully customizable** colors, names, and descriptions through VS Code settings
- Supports transparency in hex colors (8-digit format: `#RRGGBBAA`)

### 💾 Automatic Persistence
- Highlights are **automatically saved** to `highlights.json` in your workspace
- **Restores highlights** when reopening files or restarting VS Code
- Workspace-specific storage keeps projects organized

### 🔘 Quick Toggle Control
- **Status bar button** to quickly enable/disable all highlights
- Visual indicator shows current state (**"Highlights ON"** 🟢 or **"Highlights OFF"** 🔴)
- Perfect for presentations or focusing on clean code

### 🎯 Smart Selection Management
- **Right-click context menu** for quick highlighting
- **Smart removal by proximity** - select any portion near a highlight to remove it
- Automatic detection of existing highlights in selection
- Remove highlights that match, contain, or are near your selection

### 📝 Rich Documentation Support
- Each color can have a **name and description**
- Hover over highlights to see detailed information
- Metadata saved in `highlights.json` for team collaboration

### ⚡ Performance Optimized
- Efficient decoration management
- Real-time updates as you type
- Works seamlessly with large codebases

### 🔗 Integration Ready
Works complementarily with [Modules From Colors](https://github.com/AmazingCrab/Modules-From-Colors-Extension-for-VsCode) - generate code modules and architecture from your color-coded sections!

---

## 🚀 Getting Started

### Installation
1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X` or `Cmd+Shift+X`)
3. Search for **"Code Highlighter"**
4. Click **Install**
5. Start highlighting! 🎨

### Basic Usage

1. **Open a workspace** in VS Code
2. **Select text** in your editor
3. **Right-click** and choose "Add code highlight"
4. **Choose a color** from the architectural layer menu
5. **Save your file** (`Ctrl+S`) - highlights are persisted automatically

### Removing Highlights

There are **four ways** to remove highlights:

#### 1️⃣ Remove by Proximity (Smart Selection)
1. **Select any portion of code** near or within a highlighted area
2. **Right-click** and choose "Add code highlight"
3. Select **"Remove code highlights in selection"** (appears as first option)
4. The extension will **automatically detect and remove** any highlights that:
   - Exactly match your selection
   - Contain your selection
   - Are in proximity to your selection
5. Perfect for quickly cleaning up highlighted sections!

#### 2️⃣ Manual Edit via highlights.json
1. **Toggle highlights OFF** first (click status bar button or use Command Palette)
2. Open `highlights.json` in your workspace root
3. **Edit or delete** the specific color entries you want to remove
4. **Save the file**
5. Toggle highlights **back ON** to see changes
6. ⚠️ **Important**: You must disable highlights before editing the JSON file manually

#### 3️⃣ Clear All Highlights in Current File
- Open **Command Palette** (`Ctrl+Shift+P`)
- Type and select: `Code Highlighter: Clear current file code highlights`
- All highlights in the active file will be removed

#### 4️⃣ Clear All Highlights in Entire Workspace
- Open **Command Palette** (`Ctrl+Shift+P`)
- Type and select: `Code Highlighter: Clear all code highlights`
- Confirm the action
- **All highlights** from all files will be deleted, including the `highlights.json` file

### Toggle Highlights
- Click the **status bar button** (bottom right) to enable/disable all highlights
- Shows **"Highlights ON"** (green) or **"Highlights OFF"** (red)
- Or use the Command Palette: `Code Highlighter: Show quick actions menu`
- **Note**: Toggling OFF only hides highlights temporarily - they're not deleted
- **Must be OFF** when manually editing `highlights.json`

---

## 🎨 Customization

### Custom Colors Configuration

You can customize all colors, names, and descriptions in your VS Code settings:

**File** → **Preferences** → **Settings** → Search for **"Code Highlighter"**

Or edit your `settings.json`:

```json
{
  "codeHighlighter.customColors": [
    {
      "name": "Authentication Module",
      "description": "User login, JWT tokens, OAuth integration",
      "value": "#FF6B6B40"
    },
    {
      "name": "Database Layer",
      "description": "Database queries, repositories, and schema definitions",
      "value": "#4ECDC440"
    },
    {
      "name": "API Endpoints",
      "description": "REST API routes and request handlers",
      "value": "#45B7D140"
    },
    {
      "name": "Business Logic",
      "description": "Core business rules and service layer",
      "value": "#FFA50040"
    }
  ]
}
```

### Color Format
- Use hex colors with 6 digits: `#RRGGBB`
- Or with transparency (8 digits): `#RRGGBBAA`
- Example: `#FF6B6B40` = Red with 25% opacity (40 in hex = ~25%)

### Available Settings

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `codeHighlighter.defaultColor` | string | `#4A90E240` | Default highlight color |
| `codeHighlighter.saveHighlights` | boolean | `true` | Save highlights to highlights.json |
| `codeHighlighter.showStatusBar` | boolean | `true` | Show toggle button in status bar |
| `codeHighlighter.saveColorMetadata` | boolean | `true` | Save color names and descriptions |
| `codeHighlighter.customColors` | array | (see above) | Custom color definitions |

---

## ⌨️ Commands

Access these commands through the **Command Palette** (`Ctrl+Shift+P` or `Cmd+Shift+P`):

| Command | Description |
|---------|-------------|
| `Code Highlighter: Add code highlight` | Highlight selected text |
| `Code Highlighter: Clear current file code highlights` | Remove all highlights from active file |
| `Code Highlighter: Clear all code highlights` | Remove all highlights from entire workspace |
| `Code Highlighter: Reload code highlights from file` | Reload from highlights.json |
| `Code Highlighter: Show code highlights status` | Display highlight statistics |
| `Code Highlighter: Show quick actions menu` | Open quick actions menu |

### Context Menu
- **Right-click** on selected text → "Add code highlight"

---

## ⌨️ Keyboard Shortcuts

Add custom keybindings in your `keybindings.json`:

```json
[
  {
    "key": "ctrl+alt+h",
    "command": "code-highlighter.addHighlight",
    "when": "editorHasSelection"
  },
  {
    "key": "ctrl+alt+c",
    "command": "code-highlighter.clearHighlights",
    "when": "editorTextFocus"
  },
  {
    "key": "ctrl+alt+t",
    "command": "code-highlighter.toggleHighlights"
  }
]
```

---

## 📁 highlights.json Structure

The extension creates a `highlights.json` file in your workspace root:

```json
{
  "files": {
    "src/auth/login.js": {
      "#FF6B6B40": [
        {
          "startLine": 10,
          "startCharacter": 0,
          "endLine": 25,
          "endCharacter": 2,
          "name": "Authentication Module",
          "description": "User login, JWT tokens, OAuth integration"
        }
      ]
    },
    "src/db/repository.js": {
      "#4ECDC440": [
        {
          "startLine": 5,
          "startCharacter": 0,
          "endLine": 30,
          "endCharacter": 1,
          "name": "Database Layer",
          "description": "Database queries and repositories"
        }
      ]
    }
  }
}
```

This file can be:
- **Committed to version control** for team collaboration
- **Ignored** (add to `.gitignore`) for personal organization
- **Shared** across team members to maintain consistent code organization

---

## 💡 Use Cases

### 🏗️ Architecture Planning
Mark different architectural layers (MVC, layered architecture, clean architecture) with distinct colors.

### 🔍 Code Review
Highlight areas that need attention, refactoring, or special review.

### 📚 Learning & Documentation
Color-code different concepts when studying new codebases or teaching others.

### 🧩 Module Identification
Visually separate different modules or features before extracting them.

### ♻️ Refactoring Projects
Mark code sections that belong to different target modules during large refactorings.

---

## 💖 Support the Project

If **Code Highlighter** helps you work better, consider supporting its development:

<div align="center">

[![Ko-fi](https://img.shields.io/badge/☕_Buy_me_a_coffee-FF5E5B?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/amazingcrab)
[![GitHub Sponsors](https://img.shields.io/badge/💝_Sponsor_on_GitHub-EA4AAA?style=for-the-badge&logo=github-sponsors&logoColor=white)](https://github.com/sponsors/AmazingCrab)

</div>

### Other Ways to Support:
- ⭐ **Star this repository** - Helps others discover the extension
- 🐛 **Report bugs** - Help improve the extension
- 💡 **Suggest features** - Share your ideas
- 📢 **Share with your team** - Spread the word
- ✍️ **Write a review** - Share your experience on VS Code Marketplace

Your support helps me dedicate more time to developing features, fixing bugs, and maintaining this project. Every contribution, big or small, is greatly appreciated! 🙏

---

## 🔧 Requirements

- **VS Code version**: 1.60.0 or higher
- **Workspace**: Must have a folder/workspace open to save highlights

---

## 🐛 Known Issues

- Highlights may shift slightly when editing code above highlighted sections
- Very large files (>10,000 lines) with many highlights may experience minor performance impact
- Highlights are position-based, not content-based (they may move if code is edited)

---

## 🔄 Related Extension

**[Modules From Colors](https://github.com/AmazingCrab/Modules-From-Colors-Extension-for-VsCode)**  
Generate code modules and architecture from your color-coded sections. The perfect companion for Code Highlighter!

---

## 📝 Release Notes

### 1.0.0 (Initial Release)
- ✨ Architecture-focused color presets
- 💾 Automatic persistence with highlights.json
- 🔘 Status bar toggle for quick enable/disable
- 📝 Color metadata with names and descriptions
- 🎯 Smart selection and removal by proximity
- ⚡ Optimized performance
- 🎨 Full customization support

---

## 🤝 Contributing

Found a bug or have a feature request?  
**Open an issue**: [Code Highlighter Issues](https://github.com/AmazingCrab/Extension-for-VsCode-Code-Highlighter/issues)

Want to contribute code?
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📧 Contact

**Developer**: Emanuel Conte (AmazingCrab)  
**Email**: emanuel.conte.work@gmail.com  
**Ko-fi**: [ko-fi.com/amazingcrab](https://ko-fi.com/amazingcrab)

Want to collaborate or chat about the extension? Feel free to reach out!

---

## 🔗 Links

- **Repository**: [github.com/AmazingCrab/Extension-for-VsCode-Code-Highlighter](https://github.com/AmazingCrab/Extension-for-VsCode-Code-Highlighter)
- **VS Code Marketplace**: (Add your link after publishing)
- **Report Issues**: [GitHub Issues](https://github.com/AmazingCrab/Extension-for-VsCode-Code-Highlighter/issues)
- **Support**: [Ko-fi](https://ko-fi.com/amazingcrab)

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE.md](LICENSE.md) file for details.

```
MIT License - Copyright (c) 2025 Emanuel Conte (AmazingCrab)
```

---

## ⭐ Show Your Support

If you find this extension helpful:
- ⭐ **Star the repository** on GitHub
- ☕ **[Buy me a coffee](https://ko-fi.com/amazingcrab)** on Ko-fi
- 📝 **Leave a review** on the VS Code Marketplace
- 🐛 **Report bugs** or suggest features
- 📢 **Share** with your developer friends!

---

<div align="center">

**Made with ❤️ by [Emanuel Conte (AmazingCrab)](https://github.com/AmazingCrab)**

*Happy Coding! 🎨✨*

</div>