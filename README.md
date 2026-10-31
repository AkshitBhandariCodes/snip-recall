# SnipWise - Smart Clipboard Manager

For this security-cleaned source export and Mac setup, start with [HANDOFF.md](HANDOFF.md).

A powerful browser extension that intelligently manages your clipboard with instant format conversion. Copy anything, convert it to any format, and access your clipboard history whenever you need it.


## 🚀 Features

### Intelligent Clipboard Capture
- **Auto-Capture**: Automatically stores everything you copy (text, images, URLs, code, colors)
- **Smart Detection**: Intelligently categorizes clipboard content by type
- **Image Support**: Automatic screenshot and image clipboard detection
- **Zero Overhead**: Lightweight background monitoring with minimal performance impact

### Format Conversion
Convert between multiple formats instantly:

#### 📝 Code Conversions
- JSON ↔ YAML bidirectional conversion
- JSON Beautify & Minify
- Syntax-aware formatting

#### 🎨 Color Conversions
- Multiple color format support:
  - HEX, RGB, RGBA
  - HSL, HSLA, HSV
  - Named colors with luminance analysis
  - Light/Dark detection

#### 📄 Text Conversions
- Markdown ↔ HTML conversion
- **Case Transformations**: 
  - camelCase, PascalCase, snake_case
  - kebab-case, CONSTANT_CASE
  - Sentence case, dot.case, path/Case

#### 🔗 URL Tools
- QR Code generation with customizable colors
- URL encode/decode with proper handling

### Organization & Management
- **Folder System**: Organize clips into custom folders
- **Tagging**: Tag and categorize your clips
- **Pinning**: Keep important items easily accessible
- **Dashboard**: Beautiful dashboard view of all your clips

### Privacy First
- **100% Private**: Zero backend servers - everything stored locally
- **Local Storage**: Uses browser's IndexedDB for secure local storage
- **No Data Transmission**: No clipboard content ever leaves your device
- **User Controlled**: Full control over what gets captured and stored

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI Library
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first styling
- **Vite** - Fast build tool

### State Management & Storage
- **Zustand** - Lightweight state management
- **Dexie** - IndexedDB wrapper for local storage


## 📦 Use Extension
https://chromewebstore.google.com/detail/famonbgbkkjefhfmpiedfilgimjaanbl?utm_source=item-share-cb

## 📂 Project Structure

```
SnipWise-Extension/
├── src/
│   ├── popup/                 # Main popup interface
│   │   ├── App.tsx           # Popup component
│   │   ├── components/        # Reusable UI components
│   │   ├── hooks/             # Custom React hooks
│   │   └── store/             # Zustand store
│   ├── dashboard/             # Dashboard view
│   ├── options/               # Settings page
│   ├── content/               # Content script
│   ├── background/            # Service worker
│   ├── lib/
│   │   ├── converters/        # Format conversion logic
│   │   ├── db.ts              # Database operations
│   │   ├── categorizer.ts     # Content type detection
│   │   └── utils.ts           # Utility functions
│   ├── styles/                # Global styles
│   └── types/                 # TypeScript types
├── public/                    # Static assets
│   ├── manifest.json          # Extension manifest
│   └── icons/                 # Extension icons
├── vite.config.ts            # Vite configuration
├── tailwind.config.js         # Tailwind configuration
└── package.json               # Dependencies and scripts
```

## 🎯 How It Works

### Capturing
1. **Popup Open**: When you open the popup, it captures the current clipboard content
2. **Background Polling**: Service worker polls clipboard every second for new content
3. **Smart Detection**: Content is automatically categorized (text, code, color, URL, image)
4. **Storage**: Items are stored in IndexedDB with metadata (timestamps, word count, language, etc.)

### Converting
1. Open the popup and find the content you want to convert
2. Click on the conversion icon
3. Select your desired output format
4. Click to copy the converted result

### Organizing
- Create folders to organize your clips by project or category
- Use tags for flexible categorization
- Pin frequently used items for quick access


## 📋 Browser Support

- **Chrome** 90+
- **Edge** 90+
- **Firefox** 109+ (with minor adjustments)
- **Opera** 76+

## 🔐 Privacy & Security

- ✅ All data stored locally in your browser
- ✅ No cloud sync (intentional design)
- ✅ No tracking or analytics
- ✅ No account required
- ✅ Open source for transparency
- ✅ Full control over data deletion

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙋 Support

If you encounter any issues or have questions:
1. Check existing GitHub issues
2. Create a new issue with detailed information
3. Include your browser version and OS

## 🗺️ Roadmap

- [ ] Cloud sync option (encrypted, optional)
- [ ] Keyboard shortcuts customization
- [ ] More conversion formats
- [ ] Export/Import functionality
- [ ] Team collaboration features
- [ ] Performance optimizations

## 👨‍💻 Author

**Akshit Bhandari**

---

Made with ❤️ for productivity enthusiasts
