# Chronicle — Modern Blog Platform with Threaded Discussions

A high-performance blog platform and publication engine built with **modern Vanilla CSS** and **modular JavaScript (ES Modules)**, bundled and served with **Vite**.

---

## ✨ Features Overview

### 1. 📝 Core Publishing & Editing
- **Story Studio Modal**: Create new articles or edit existing ones.
- **Rich Markdown Formatting**: Live toolbar supporting Headings (H2, H3), Bold, Italic, Blockquotes, Fenced Code Blocks, Lists, Links, and Dividers.
- **Live Split Preview**: Toggle between "Edit", "Split", and "Preview" views.
- **Reading Time & Word Count**: Automatic dynamic calculation (e.g. `~4 min read · 720 words`).
- **Cover Image Selector**: Pick from curated high-resolution editorial presets or provide custom URLs.
- **Tag Management**: Interactive chip manager (type tag and press <kbd>Enter</kbd> or comma).

### 2. 💬 Nested & Threaded Comments System
- **Multi-Level Threading**: Deeply nested replies with visual indentation and connecting branch hierarchy.
- **In-Place Reply Composer**: Slide-down reply box under any comment in the tree.
- **Live Emoji Reactions**: Quick reactions (`❤️`, `👍`, `💡`, `🔥`, `🚀`) with active user toggle and live count indicators.
- **Pinned Comments**: Authors and moderators can pin high-value comments to the top with a 📌 badge.
- **Comment Moderation & Actions**:
  - Edit comment in-place with `(edited)` indicator.
  - Delete comment with confirmation.
  - Report / flag comment for moderator review.
- **Persona Switcher**: Dropdown in the comments section to switch between different community roles (*Author*, *Tech Lead*, *Product Designer*, *Community Moderator*) to easily test multi-user conversations.

### 3. 🔍 Search, Filter & Discovery
- **Instant Search**: Real-time debounced search matching title, excerpt, full markdown content, author name, and `#tags`.
- **Category Pill Bar**: Filter across categories (*All*, *Design & UI*, *Artificial Intelligence*, *Web Development*, *Architecture*, *Productivity*).
- **Tag Cloud**: Clickable popular tags in the sidebar.
- **Sort Dropdown**: Sort by *Latest Published*, *Most Liked ❤️*, *Most Discussed 💬*, or *Quick Read*.
- **Active Filter Bar**: Interactive chips showing applied filters with a 1-click "Reset All" button.

### 4. 📖 Reading Experience & Bookmarks
- **Reader Modal**: Full-screen distraction-free reader with article hero image, author biography, and reading stats.
- **Like Interaction**: Micro-animated heart button with instant counter updates.
- **Bookmark / Reading List**: Save articles to your personal reading list; toggle between "Feed" and "Bookmarks" in the navbar.
- **Share to Clipboard**: Generates and copies clean share links.

### 5. 🎨 Design Aesthetics & Themes
- **Adaptive Dark / Light Themes**: Obsidian slate with violet/cyan neon glow in Dark mode, crisp porcelain with deep indigo accents in Light mode. Persisted in `localStorage`.
- **Modern Typography**: Google Fonts (`Outfit`, `Plus Jakarta Sans`, `Fira Code`).
- **Glassmorphism & Micro-animations**: Subtle backdrop filters, smooth hover lifts, animated modals, and slide-in toast notifications.

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v18+)
- npm

### Running Locally
```bash
# 1. Install dependencies (if not already installed)
npm install

# 2. Start Vite development server
npm run dev

# 3. Open in your browser
# http://localhost:5173
```

### Production Build
```bash
npm run build
```

---

## 📁 Project Structure

```
Blog Platform with Comments/
├── index.html                   # Semantic HTML5 shell with Google Fonts & modals
├── package.json                 # Project scripts and Vite configuration
├── README.md                    # Project documentation
└── src/
    ├── css/
    │   ├── tokens.css           # Design tokens, color palettes (Dark & Light), spacing
    │   ├── base.css             # Resets, typography, scrollbars, animations
    │   ├── layout.css           # Sticky navbar, hero showcase, grid layout, sidebar
    │   ├── components.css       # Buttons, cards, search input, modals, toasts
    │   ├── comments.css         # Threaded tree styles, reactions, inline composers
    │   └── editor.css           # Story Studio modal, split preview, markdown toolbar
    └── js/
        ├── main.js              # Application entry point & lifecycle coordinator
        ├── data/
        │   └── seedData.js      # Rich starter articles, pre-seeded nested comments & personas
        ├── store/
        │   └── blogStore.js     # Reactive state store with LocalStorage persistence
        ├── utils/
        │   ├── markdownParser.js# Markdown-to-HTML parser, reading time & relative dates
        │   └── toast.js         # Animated toast notification manager
        └── components/
            ├── themeToggle.js   # Dark/Light mode switcher with persistence
            ├── searchFilter.js  # Instant search, category tabs, active filter badges
            ├── postCard.js      # Article card with bookmarking and click-to-read
            ├── postReader.js    # Article reader modal with like, share & comments mount
            ├── commentSection.js# Threaded comment tree, reactions, moderation
            ├── postEditor.js    # Post creator/editor modal with live split preview
            └── sidebar.js       # Trending tags & community activity stats widgets
```

---

## 💾 State Persistence
All created articles, edits, deletions, comments, nested replies, emoji reactions, and theme preferences are automatically saved to the browser's `localStorage`. You can reset back to the default demonstration dataset at any time using the **"Reset to Demo Data"** button in the sidebar.
