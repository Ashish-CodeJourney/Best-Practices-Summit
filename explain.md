# Project Explanation: Best Practices Summit

## 1. Project Overview
**Best Practices Summit** is a modern, responsive static website designed for a high-profile cybersecurity networking event. The platform serves as the digital hub for the summit, providing event details, attendee networking features, and an interactive badge generation tool.

The target audience includes CISOs, CXOs, and cybersecurity professionals from various industries (FinTech, HealthTech, etc.).

## 2. Technology Stack
The project is built using standard web technologies without a complex backend or compilation step.

-   **Core:** HTML5, CSS3, Vanilla JavaScript (ES6+).
-   **Frameworks & Libraries:**
    -   **Bootstrap 5**: For responsive layout and UI components (modals, carousel).
    -   **FontAwesome**: For icons.
    -   **Gumshoe**: For scroll-spy navigation.
    -   **Google Fonts**: Inter, Montserrat, Prompt, and Roboto.
-   **Architecture:** Static Site with Client-Side Rendering (CSR) for dynamic content.

## 3. Directory Structure
```text
/
├── assets/
│   ├── css/            # Stylesheets (theme.css, inline.css)
│   ├── js/             # Logic (main.js, badge-generator.js)
│   ├── images/         # Assets including badge frames
│   ├── data/           # JSON data sources (e.g., attendees.json)
│   ├── includes/       # HTML partials (header.html, footer.html)
│   └── plugins/        # Third-party libraries
├── index.html          # Main landing page
├── create-badge.html   # Badge generator tool
├── README.md           # Project documentation
└── ... (auxiliary pages like privacy.html, terms.html)
```

## 4. Key Features & Functionality

### 4.1 Landing Page (`index.html`)
The main entry point features a "premium" design aesthetic with:
-   **Hero Section:** Animated geometric background (3D particle effects) and an event carousel.
-   **Dynamic Content:**
    -   **Countdown Timer:** JavaScript-driven countdown to the event date.
    -   **Attendee List:** Fetches data from `assets/data/attendees.json` and renders attendee cards dynamically (handled by `main.js`).
-   **Sections:** Statistics, About, Topics Covered, Key Highlights, and Event Outcomes.

### 4.2 Badge Generator (`create-badge.html`)
A standout feature allowing attendees to create custom event badges.
-   **Logic:** `assets/js/badge-generator.js`
-   **Capabilities:**
    -   **Input:** User provides Name, Photo, and selects a Role (Speaker, Attendee, Volunteer).
    -   **Layouts:** Supports Portrait, Landscape, and Square formats.
    -   **Canvas Rendering:** Uses HTML5 Canvas to composite the user's photo with pre-designed frame assets (`assets/images/badge-frames/`).
    -   **Download:** Generates a PNG file for the user to download.

### 4.3 Component System
Although static, the site uses a lightweight client-side include system:
-   **`assets/js/include-partials.js`**: Automatically fetches and injects `header.html` and `footer.html` into placeholders (e.g., `<div data-include="...">`). This ensures consistency across pages without a server-side templating engine.

## 5. Development & Customization
-   **Theme:** Colors and fonts are defined in `assets/css/theme.css`. The design leans heavily on a blue/purple gradient palette (`#667eea` to `#764ba2`).
-   **Data:** To update attendees, modify `assets/data/attendees.json` instead of editing HTML.
-   **Frames:** Badge designs are image-based; changing the badge look requires updating images in `assets/images/badge-frames/`.
