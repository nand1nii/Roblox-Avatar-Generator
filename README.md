# 🎮 Roblox Avatar Generator

A browser-based, zero-dependency Roblox-style avatar creator built entirely with vanilla HTML, CSS, and JavaScript. Design your character in real time, randomize it, export it as a PNG, and share it via a URL.

**🌐 Live Demo:** [roblox-avatar-generator.vercel.app](https://roblox-avatar-generator.vercel.app)

---

## ✨ Features

- **8 customizable categories** — Body, Head, Face, Hair, Shirt, Pants, Shoes, and Accessories
- **10+ style options per category** — Classic, Rthro, Blocky, Mohawk, Cargo pants, Crocs, Wings, Halo, and more
- **Custom color pickers** — Skin, hair, shirt, and pants colors with preset swatches and hex input
- **Live SVG preview** — Avatar renders instantly in the browser with no page reloads
- **Randomize button** — Generate a random outfit in one click
- **Export as PNG** — Save your avatar directly to your device
- **Shareable link** — Encode your full avatar config into the URL to share with others
- **Responsive design** — Works on desktop and mobile with a collapsible tab bar on small screens
- **No dependencies** — Pure HTML/CSS/JS, no frameworks or build steps required

---

## 🗂 Project Structure

```
Roblox-Avatar-Generator/
├── index.html          # Entire app — markup, styles, and scripts in one file
├── launch.json         # VS Code launch configuration
├── settings.local.json # Local editor settings
└── README.md
```

---

## 🚀 Getting Started

### Option 1 — Open directly in your browser

No build step or server needed. Just clone the repo and open `index.html`:

```bash
git clone https://github.com/nand1nii/Roblox-Avatar-Generator.git
cd Roblox-Avatar-Generator
open index.html   # macOS
# or double-click index.html in your file explorer
```

### Option 2 — Use a local dev server (recommended for share links)

URL-based sharing requires a proper origin. Use any static server:

```bash
# With Python
python3 -m http.server 8080

# With Node.js / npx
npx serve .

# With VS Code
# Install the "Live Server" extension and click "Go Live"
```

Then visit `http://localhost:8080` in your browser.

---

## 🎨 Customization Options

| Category    | Options |
|-------------|---------|
| **Body**    | Classic, Rthro, Rthro Narrow, Blocky, Stylish, Boy, Girl, Rthro Tall, Rthro Short, Custom |
| **Head**    | Standard, Round, Rthro, Square, Pointy, Oval, Alien, Pumpkin, Candy, Diamond |
| **Face**    | Smile, Worried, Sunglasses, Bandana, Freckles, Blush, Shocked, Cyclops, Robot Visor, Derp |
| **Hair**    | None, Messy, Spiky, Ponytail, Curly, Bun, Mohawk, Side Part, Afro, Pigtails, Long Straight, Long Curly |
| **Shirt**   | Tee, Hoodie, Suit, Tank, Jersey, Armor, Lab Coat, Cape, Flannel, Jacket |
| **Pants**   | Jeans, Shorts, Slacks, Cargo, Leggings, Swim Trunks, Overalls, Plaid, Joggers, Ripped |
| **Shoes**   | Sneakers, Boots, Sandals, High-Tops, Loafers, Cleats, Moccasins, Platforms, Slippers, Crocs |
| **Accessory** | None, Crown, Headphones, Sling Bag, Wings, Sword, Shield, Rose, Necklace, Halo |

Color pickers are available for skin tone, hair, shirt, and pants.

---

## 🛠 How It Works

The app is a single self-contained `index.html` file organized in three sections:

**1. Data** — All categories, item lists, and color palettes are defined as plain JavaScript arrays/objects at the top of the script.

**2. State** — A simple `state` object tracks the current selections (body type, colors, items). Defaults are defined in a `DEFAULTS` constant.

**3. SVG Renderer** — A set of drawing functions (`drawHead`, `drawHair`, `drawShirt`, `drawPants`, etc.) build the avatar by injecting SVG elements into the preview area. Each part is layered in the correct draw order (back to front) to achieve realistic compositing — for example, wings render behind the body and capes render behind the torso.

Helper utilities like `darken()` and `lighten()` manipulate hex colors to generate shadows and highlights procedurally.

---

## 📱 Responsive Layout

| Breakpoint | Layout |
|------------|--------|
| `> 900px`  | Three-column layout — sidebar on left, avatar center, picker on right |
| `≤ 900px`  | Single-column — mobile tab bar at the bottom, picker stacks below avatar |
| `≤ 500px`  | Compact grid (2 columns) in picker, smaller avatar preview |

---

## 🧩 Tech Stack

- **HTML5** — Single-file app structure
- **CSS3** — Custom properties (variables), Flexbox, Grid, media queries
- **Vanilla JavaScript (ES6+)** — No frameworks, no build tools
- **SVG** — Procedurally generated avatar graphics
- **Google Fonts** — [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) for the retro pixel aesthetic
- **Vercel** — Hosting and deployment

---

## 🤝 Contributing

Contributions are welcome! Here are some ideas:

- Add new hair styles, accessories, or body types
- Add background/scene selection for the avatar
- Add animation (idle bounce, wave)
- Improve mobile UX
- Add a gallery to browse saved avatars

To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-new-style`)
3. Make your changes in `index.html`
4. Commit and push (`git push origin feature/my-new-style`)
5. Open a Pull Request

---

## 📄 License

This project is open source. See the repository for details.

---

> Made with ❤️ by [nand1nii](https://github.com/nand1nii)
