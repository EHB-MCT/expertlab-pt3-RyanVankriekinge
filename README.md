# Dynamic Transitions Portfolio

This project is a personal portfolio that uses web animations and transitions.

## Project set-up guide

### Requirements

Make sure you have the following installed: <br>
**Node.js** (version 18 recommended)<br>
**npm** (version 9 recommended)

### Node installation

Check your node version with <br> `node -v`<br>

If you don't have Node.js and npm installed, download and install the latest stable version from [Node.js official website](https://nodejs.org/en/download/package-manager)

### Dependency installation

To install the dependencies, run the following command <br> `npm install`

### Running the application

To start the development server, run <br>
`npm run dev`

## Linting and formatting

This project uses ESLint and Prettier for code linting and formatting <br><br>
To check for linting errors, run: <br>
`npm run lint`<br><br>
To fix formatting issues, run: <br>
`npm run format`

## References

1. **Creating .gitignore file**  
   Used gitignore.io to generate a suitable .gitignore file for a Node.js project.

2. **Initialising Vue project in existing project**  
   Used [How to guide: Adding VueJS to your existing project](https://www.codemotion.com/magazine/frontend/javascript/how-to-guide-adding-vuejs-to-your-existing-project/) to initialise Vue in my existing project

3. **Finding media screen width breakpoints**  
   Used [Media queries: How to target desktop, tablet and mobile?](https://stackoverflow.com/questions/6370690/media-queries-how-to-target-desktop-tablet-and-mobile) to find ideal breakpoints for different screen sizes, used in assets > \*

4. **Creating animated hamburger menu in Vue**  
   Used [Vue Tutorial: How to make a responsive hamburger menu](https://piboutique.com/vue-tutorial-how-to-make-a-responsive-burger-menu/) to create mobile menu in src > views > App.vue and in src > components > HamburgerMenu.vue

5. **Using transitions in Vue**  
   Used [Vue.js 3 GreenSock (GSAP) Animating Tutorial](https://www.koderhq.com/tutorial/vue/animation-greensock-gsap/) to use GSAP animations in Vue, in src > \*

6. **Adding a stagger to all list items inside an unordered list**  
   Used [ChatGPT](https://chatgpt.com/share/672de058-d320-8002-9968-b17f2d091bc4) to add a stagger to my mobile menu animation in src > App.vue
