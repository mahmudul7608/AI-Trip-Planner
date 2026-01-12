# AI Trip Planner

![AI Trip Planner Screenshot](https://github.com/user-attachments/assets/df7cdefb-cd34-4a6b-b58f-7ee0804f5e8a)

A beautiful **AI-powered trip planning** application built with **Nuxt 3** and **Tailwind CSS**  lightweight, responsive, and designed for real-world trip creation.

---

#Live Link : https://new-ai-trip-planner-web.netlify.app/

## Features

* Generate itinerary suggestions using AI prompts
* Search and filter destinations
* Save and export trip plans
* Responsive UI built with Tailwind CSS
* Clean component structure using Nuxt 3 composables

---

##  Tech Stack

* **Framework:** Nuxt 3
* **Styling:** Tailwind CSS
* **State / API:** Pinia / composables (or your preferred solution)
* **Backend (optional):** Firebase / MongoDB (configurable)

---

##  Setup

Clone the repo and install dependencies:

```bash
yarn install
# or
npm install
```

Create a `.env` file at the project root (if needed) and add any environment variables your app requires, for example:

```
NUXT_PUBLIC_API_BASE_URL=https://api.example.com
OPENAI_API_KEY=sk-xxxx
```

> Keep secrets out of source control. Use environment variables or a secrets manager.

---

##  Development

Run the development server locally (hot reload):

```bash
yarn dev
# or
npm run dev
```

Open: `http://localhost:3000`

---

##  Production

Build for production:

```bash
yarn build
# or
npm run build
```

Preview the production build locally:

```bash
yarn preview
# or
npm run preview
```

For deployment, check the official Nuxt 3 docs: `https://nuxt.com/docs/getting-started/deployment`.

---

##  Project Structure (recommended)

```
/ — root
  /components — Vue components
  /composables — composable logic
  /pages — Nuxt pages
  /assets — images, fonts
  /styles — Tailwind configuration + globals
  /utils — helpers
  nuxt.config.ts
  package.json
```

---

##  Helpful Scripts

```json
{
  "dev": "nuxt dev",
  "build": "nuxt build",
  "preview": "nuxt preview",
  "lint": "eslint --ext .js,.ts,.vue ."
}
```

---

##  Contributing

Contributions are welcome! Please open issues for bugs or feature requests and create PRs for changes.

Suggested workflow:

1. Fork the repo
2. Create a feature branch: `git checkout -b feat/my-feature`
3. Commit and push
4. Open a Pull Request

---

##  License

Specify your license here (MIT, Apache-2.0, etc.). Example: `MIT`.

---
