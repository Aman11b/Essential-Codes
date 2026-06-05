# 🚀 React + Vite Project Setup

A quick guide for creating a clean React project with Vite and ESLint.

---

## 1. Create a New Vite Project

```bash
npm create vite@latest
```

### Choose:

```text
Project Name → your-project-name
Framework    → React
Variant      → JavaScript
```

Install dependencies:

```bash
cd your-project-name
npm install
```

```bash
code .
```
> to open vscode

---

## 2. Configure ESLint

Install ESLint and related packages:

```bash
npm install --save-dev eslint eslint-config-react-app vite-plugin-eslint
```

Create a `.eslintrc.json` file in the root directory:

```json
{
  "extends": "react-app"
}
```

---

## 3. Configure Vite

Update `vite.config.js`:

```javascript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import eslint from 'vite-plugin-eslint';

export default defineConfig({
  plugins: [react(), eslint()],
});
```

---

## 4. Remove Default Starter Files

Delete:

```text
src/assets/
src/App.css
src/index.css
```

---

## 5. Clean Up `main.jsx`

Remove:

```javascript
import './index.css';
```

Final `main.jsx`:

```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

---

## 6. Clean Up `App.jsx`

Replace everything with:

```javascript
function App() {
  return <h1>Hello React 🚀</h1>;
}

export default App;
```

---

## 7. Run the Development Server

```bash
npm run dev
```

---

## Optional Folder Structure

```text
src/
│
├── components/
├── features/
├── pages/
├── services/
├── utils/
├── App.jsx
└── main.jsx
```

---

Happy coding! 🚀
