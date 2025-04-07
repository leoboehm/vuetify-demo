# Vuetify Demo Project

This project demonstrates the integration and usage of **Vuetify 3** in a Vue 3 application using **Vite**. It showcases a minimal yet practical UI setup including a card, dialog, slider, progress bar, and a dark/light mode toggle.

## 📦 Tech Stack

- [Vue 3](https://vuejs.org/)
- [Vuetify 3](https://next.vuetifyjs.com/)
- [Vite](https://vitejs.dev/)

---


## 🧰 Prerequisites

Make sure the following tools are installed on your system:

### ✅ Node.js and npm

Check if installed:

```bash
node -v
npm -v
```

### ✅ Vue CLI (Usually optional for custom setups, but will be used to install Vuetify in the upcoming toturial)

Install globally using npm:

```bash
npm install -g @vue/cli
```

Check version:

```bash
vue --version
```

---


## 📚 Setting up a Vue 3 + Vuetify 3 Project with Vue CLI (Alternative)
If you prefer to create your own project instead of using the demo out-of-the-box, follow these steps:

```bash
vue create demo-project
cd demo-project
```

During setup, choose:
- Vue 3 preset

Run your project:

```bash
npm run serve
```

---


## 🚀 Getting Started with the Demo Project

The demo project will be used for the lecture, so it's pretty empty right now.<br>
If you wish to have a look at and experiment with the final project, you will find this in the directory `demo-project-completed`.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/vuetify-demo.git
cd vuetify-demo/demo-project
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the Application Server

```bash
npm run serve
```

The app will be available at `http://localhost:8080` by default.

---

## 🧩 Project Structure

```
src/
├── components/
│   ├── DemoCard.vue          # Vuetify card component
│   ├── DialogExample.vue     # Simple Vuetify dialog
│   └── ThemeToggle.vue       # Dark/light mode toggle switch
├── App.vue                   # Main application layout
└── main.js                   # Vuetify setup and app mounting
```

---

## 🖥️ Features Demonstrated

### ✅ Vuetify Integration
- Vuetify is installed and initialized via `vite-plugin-vuetify`.
- All components and directives are globally registered.

### ✅ Theming (Dark/Light Toggle)
- Implemented using Vuetify's theme system.
- Controlled via `ThemeToggle.vue` with a `v-switch`.

```vue
<v-switch v-model="isDark" label="Dark Mode" @change="toggleTheme" />
```

### ✅ Card Component
- `DemoCard.vue` uses `v-card`, `v-img`, and `v-card-text`.

```vue
<v-card>
  <v-img src="..." height="200px" cover></v-img>
  <v-card-title>Vuetify Card</v-card-title>
</v-card>
```

### ✅ Dialog Component
- `DialogExample.vue` uses `v-dialog` and a `v-btn` to open it.

```vue
<v-dialog v-model="dialog">
  <template #activator="{ props }">
    <v-btn v-bind="props">Open Dialog</v-btn>
  </template>
</v-dialog>
```

### ✅ Progress Bar + Slider
- `App.vue` uses a `v-slider` to control the value of a `v-progress-linear`.

```vue
<v-slider v-model="progress" max="100" />
<v-progress-linear :model-value="progress" />
```

---

## 📖 Learn More

- Vuetify 3 Documentation: https://vuetifyjs.com
- Vue 3 Documentation: https://vuejs.org

---

## 📌 License

This project is intended for educational purposes and demonstration. You are free to modify and reuse it.
