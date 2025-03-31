# 🔅 TerraHQ Frontend Trial

## 📌 Project Description

This project is a landing page based on the provided Figma design. The SPA is built with **Vue 3**, **Vite**, and **Tailwind CSS**, and dynamically retrieves its content from a given REST API.

Here you can see the site deployed on Netlify:

🔗 [TERRA TRIAL - DEPLOY](https://terrahq-fe-trial.netlify.app/)

![420shots_so](https://github.com/user-attachments/assets/56e5fa53-3c9e-4505-bc21-5d362efe34ae)


## 📝 Requirements

1. The page must be fully responsive and adaptable to desktop, tablet, and mobile.

2. Implement hover effects on buttons based on the given visual reference.

3. Use the Manrope font (Google Fonts).

4. Get content and images from the provided REST API: [https://tf-frontend.netlify.app/trial](https://tf-frontend.netlify.app/trial).

5. The page layout changes depending on the first or subsequent accesses, and must manage this state with localStorage and follow the different layouts provided depending on the state.

6. Any frontend framework is allowed.


## 💥 Key Development Decisions
### 🛠️ **Technology Choice**
- **Vue 3 + Vite**: Chosen for their speed of development, responsiveness, and ease of configuration with components.
- **Tailwind CSS**: Allows for flexible and modular design without the need to write extensive custom CSS. It's also a personal choice based on my daily use of this framework.

### 🔄 **User Access State Manager**
- **Using `localStorage` in `Hero.vue`** to check if the user has already visited the page and change the button text accordingly.
- **Why did I manage it in the component and not in `App.vue`?**: The main reason is that this state is only necessary and produces changes in the `Hero.vue` component. Therefore, by managing it this way, we keep each component self-contained and avoid unnecessary prop drilling.

### 🌀 **Render Components Dynamically**
- **API Fetch**: The page structure is obtained from the API using `fetch()` and the components are rendered dynamically in `App.vue`.
- `App.vue` obtains the page structure from the API and renders components based on the data, allowing the page structure to adapt if the data changes in the future without modifying the frontend code, as is the case with CMS integrations.


## 🚀 Project Deployment
### 🏗️ **Local Installation and Execution**
```sh
# Clone the repository
git clone https://github.com/mherrezu/terrahq-fe-trial
cd <repository>

# Install dependencies
bun install

# Run the development environment
bun run dev
```

### 🌍 **Deploy to Production**
```sh
# Compile the application for production
bun run build

# Serve the compiled version
bun run preview
```
## Tech Stack

<a href="https://vuejs.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" alt="vuejs" width="40" height="40"/> </a>
<a href="https://vitejs.dev/" target="_blank" rel="noreferrer"><img src="https://github.com/dochne/wappalyzer/blob/main/src/images/icons/vite.svg" alt="vite" width="40" height="40"/></a>
<a href="https://tailwindcss.com/" target="_blank" rel="noreferrer"><img src="https://github.com/dochne/wappalyzer/blob/main/src/images/icons/tailwindcss.svg" alt="tailwindcss" width="40" height="40"/></a>

### ☁️ **Hosting**
- [Netlify](https://www.netlify.com/).

---
Any feedback is welcome! 😊

