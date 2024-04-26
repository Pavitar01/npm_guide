# Creating an NPM Package for React Component

This guide outlines the steps to create an NPM package for a React component. Follow these steps to publish your React component as an NPM package for others to use.

## 1. Create Folder

Create a folder with the name corresponding to your unique package name.

```bash
mkdir your-package-name
cd your-package-name
```
## 2. Initialize NPM
Inside the folder, initialize NPM by running the following command in the terminal:

```bash 
npm init -y

```
## 3. Install Dependencies
Install necessary dependencies using yarn:

```bash
yarn add @babel/cli @babel/core --dev
yarn add @babel/preset-env @babel/preset-react --dev
yarn add @babel/plugin-proposal-class-properties --dev
yarn add react-dom react --dev

```

## 4. Create .babelrc
Create a .babelrc file in the root of your project and add the following configuration:

```json 
{
    "presets": [
        [
            "@babel/preset-env",
            {
                "targets": {
                    "node": "current"
                }
            }
        ],
        "@babel/preset-react"
    ],
    "plugins": [
        "@babel/plugin-proposal-class-properties"
    ]
}

```

## 5. Add Build Command
Add the build command in the package.json script:

```bash

"scripts": {
    "build": "./node_modules/.bin/babel src --out-file index.js"
}

```

## 6. Build Package
Run the build command to compile your source code:

```bash 
yarn build
```

## 7. Publish Package
Login to NPM using your credentials:

```bash
npm login
```

#### Then publish your package:


```bash 
npm publish

```

## 8. Updating Package Version
To update the package version, make changes in the root folder, rebuild the package, and then use the following commands:

```bash 
npm version patch
npm publish

```

Make sure to update the version in your package.json before publishing.

That's it! Your React component is now available as an NPM package.


```bash 
Remember to replace `your-package-name` with your actual package name throughout the instructions.

```
