# Vuetify Demo Project

This project demonstrates the usage of **Vuetify 3** in a **Vue 3** application by implementing a small To-Do list. It showcases a minimal yet practical UI setup including a navigation bar, card, dialog, progress bar, and a dark/light mode toggle.

## 📦 Tech Stack

- [Vue 3](https://vuejs.org/)
- [Vuetify 3](https://next.vuetifyjs.com/)

---


## 🧰 Prerequisites

Make sure the following tools are installed on your system:

### ✅ Node.js and npm

Check if installed:

```bash
node -v
npm -v
```

For the unlikely case that you do not have those installed, check out the [npm documentation](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

---


## 🚀 Getting Started with the Demo Project

The demo project will be used for the lecture, so it's pretty empty right now.<br>
If you wish to have a look at and experiment with the final project, you will find this in the directory `demo-project-completed`.

### 1. Clone the Repository

```bash
git clone https://github.com/leoboehm/vuetify-demo.git
cd vuetify-demo/demo-project
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the Application Server

```bash
npm run dev
```

The app will be available at `http://localhost:3000` by default.

---

## 📚 Setting up the Vue 3 + Vuetify 3 Project yourself directly via Vuetify (Alternative)
If you prefer to create your own project instead of using the demo out-of-the-box, follow these steps:

```bash
npm create vuetify@latest
```
You will be asked to confirm the installation of `vuetify/create`, please confirm.

During setup, choose:
- Project name: demo-project
- Preset: Barebones (Only Vue & Vuetify)
- Use TypeScript: No
- Dependency management: npm
- Install Dependencies: Yes

Run your project:

```bash
cd demo-project
npm run dev
```

The app will be available at `http://localhost:3000` by default.

---


## 🧩 Project Structure

```
src/
├── components/
│   ├── NavBar.vue            # Vuetify nav bar
│   ├── Task/
│   |   ├── TaskCard.vue      # Simple Vuetify card that displays a task
│   |   ├── TaskDialog.vue    # Simple Vuetify dialog to add a new To-Do
│   |   ├── TaskList.vue      # Simple list that displays the To-Do cards
├── pages/
│   ├── ToDo.vue              # Main page
├── plugins/
│   ├── index.js              # Plugin handling
│   ├── vuetify.js            # Vuetify configuration
├── App.vue                   # Main application layout
└── main.js                   # App mounting
```

---

## 🖥️ Features Demonstrated

### ✅ Theming (Dark/Light Toggle)
- Implemented using Vuetify's theme system.

```js
const theme = useTheme();

function toggleTheme() {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
```

### ✅ Card Component
- `TaskCard.vue` uses `v-card`, `v-card-title`, and `v-card-text`.

```vue
  <v-card>
    <v-card-title>Task Title</v-card-title>
    <v-card-text>Task Description</v-card-text>
  </v-card>
```

### ✅ Dialog Component
- `TaskDialog.vue` uses `v-dialog` and a `v-btn` to open it.

```vue
    <v-btn @click="dialog = true">Add Task</v-btn>
    <v-dialog v-model="dialog" persistent max-width="400px">
      <v-card>
        <v-card-title>Add New Task</v-card-title>
        <v-card-text>
          <v-text-field v-model="title" label="Task" autofocus />
          <v-text-field v-model="text" label="Description (Optional)" />
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn text @click="dialog = false">Cancel</v-btn>
          <v-btn color="success" @click="addTask">Add</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
```

### ✅ Progress Bar
- `ToDo.vue` uses a `v-progress-linear` to show the progress of completed tasks.

```vue
    <v-progress-linear
      :model-value="completionRate"
      height="40"
      color="green"
    >
      <strong>Tasks completed: {{ completionRate }}%</strong>
    </v-progress-linear>
```

---

## 📖 Learn More

- Vuetify 3 Documentation: https://vuetifyjs.com
- Vue 3 Documentation: https://vuejs.org

---

## 📌 License

This project is intended for educational purposes and demonstration. You are free to modify and reuse it.
