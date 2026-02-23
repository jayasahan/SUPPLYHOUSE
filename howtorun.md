# How to Run — SUPPLYHOUSE (Unfake)

## Prerequisites

- **Node.js** (v18 or later recommended)
- **npm** (comes with Node.js)

## Setup & Run

1. **Open a terminal** and navigate to the project folder:

   ```bash
   cd unfake
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Start the development server:**

   ```bash
   npm run dev
   ```

   The app will be available at `http://localhost:5173` (default Vite port).

## Other Commands

| Command             | Description                        |
| ------------------- | ---------------------------------- |
| `npm run dev`       | Start development server (hot reload) |
| `npm run build`     | Type-check & build for production  |
| `npm run preview`   | Preview the production build locally |

## Tech Stack

- Vue 3 + TypeScript + Vite
- Tailwind CSS v4
- Pinia (state management)
- Vue Router 4
- Axios → DummyJSON API

## Notes

- The app uses **DummyJSON** as its backend API, so an internet connection is required.
- Cart data is persisted in **localStorage**.
- Dark / Light mode toggle is available in the navbar.
