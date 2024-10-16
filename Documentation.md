# Meeting Summary - Accomplishments and Next Steps

### What We Accomplished This Meeting
- Successfully installed Electron and React
- Ran React on Electron to display a basic interface
- Gained a partial understanding of Electron and React integration

### Action Plan for Next Meeting
- Gain a complete understanding of Electron and React
- Install Tailwind CSS (optional, but it could be very helpful)
- Draft a rough design for the website

---

# Documentation

## Frontend Development Tools
We chose **React + Electron** because this setup effectively supports our application's vision. React will manage the frontend, while Electron will allow us to package the frontend into a standalone desktop application that can run on multiple operating systems, thus eliminating the need for OS-specific dependencies.

## Getting Started Guide

1. **Install Electron**  
   In your terminal, run:
   ```
   npm init electron-app@latest <FOLDER_NAME> -- --template=webpack
   ```
This setup includes everything needed to get an Electron app running.

2. **Navigate to Your Project Folder**
```
cd <FOLDER_NAME>
```
 3. **Configure Webpack**

Open webpack.rules.js and change the line:
```
test: /\.tsx?$/ 
```
 to:
```
test: /\.jsx?$/
```
 **Note: Changing to `.jsx` allows JavaScript usage. Keep it as `.tsx` if you prefer TypeScript.**

 4. **Install Development Dependencies**
```
npm install --save-dev @babel/core @babel/preset-react babel-loader
```
 5. **Add Babel Loader to Webpack**
 
 In `webpack.rules.js`, add the following configuration at line 19:
```
 {
    test: /\.jsx?$/,
    use: {
       loader: 'babel-loader',
       options: {
          exclude: /node_modules/,
         presets: ['@babel/preset-react']
      }
    }
 }
```
 6. **Install React**
```
npm install --save react react-dom
```
 7. **Set Up React**
    
In the src folder, create an index.jsx file with the following content:
```
 import * as React from 'react';
 import { createRoot } from 'react-dom/client';

 const root = createRoot(document.body);
 root.render(<h2>Hello from React!</h2>);
```
 8. **Update Files**
    
 Update renderer.js and modify `index.css` to `index.jsx`.

 9. **Run the Application**
```
npm start
```
 This should now display a basic React-powered desktop app.

 10. **Additional Configuration for React Structure**
     
 - Create a components folder within src.
 - Inside components, create a `Home.jsx` file with:
```
 import React from 'react';

 export default function Home() {
    return (
       <div>Home</div>
    );
 }
```
 In index.jsx, replace root.render content with:
```
 <Home />
 ```
 Add .jsx to the end of './components/Home' in index.jsx.

 11. **Run the App**
```
npm start
```
 Use this to see changes reflected in the desktop app.
