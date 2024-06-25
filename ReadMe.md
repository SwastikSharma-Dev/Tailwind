# TailWind CSS 101 - Swastik Sharma

## Introduction

Tailwind CSS works by scanning all of your HTML files, JavaScript components, and any other templates for class names, generating the corresponding styles and then writing them to a static CSS file.

In simple terms, TailWind is just a tool that generates CSS Code that we requires by describing it with some shortcut keywords. Instead of writing the CSS code ourself we tell TailWind what to generate.

## Installation - ( https://tailwindcss.com/docs/installation )
1. Install Node.js (Other Methods also Available.)
2. In Terminal, go to the Desried Directory and run:
    ```sh
    npx tailwindcss init
    ```
3. The above command will initialize "**tailwind.config.js**"
4. Create Folders: "**dist**" and "**src**" for Organized Work. (*OPTIONAL*)
5. Create "**input.css**" in "**src**" folder and write:
    ```css
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
6. This will call/import/link the "*base*", "*components*", and "*utilities*" of TailWind into "**input.css**" file; which later will be used.

## Working and Using
1. Create "**index.html**" in "**dist**" folder.
2. Go to "**tailwind.config.js**" and in "***content***", give Value as the Address of the "index.html" (Working) File. It should look like:
    ```js
    content: ["./dist/index.html"]
    ```
    > In Future, More Files (other HTML Files) can be given as Parameter, as Multiple Paramters can be Passed to "content". But instead of giving arguments each time for a file, we will instead write an "Asterisk" i.e. * , which takes all the HTML files of "dist folder" as a single argument. It is written as:
    ```js
    content: ["./dist/*.html"]
    ```
3. In Terminal run:
    ```sh
    npx tailwindcss -i .\src\input.css -o .\dist\style.css
    ```
    OR
    
    ```sh
    npx tailwindcss -i .\src\input.css -o .\dist\style.css --watch
    ```
    > After "-i" you should write location of input.css file and after "-o", the location you require of the css file generated (which will be linked to html) to be stored.
    > The First Command will Generate the css file into "style.css" once and we need to Generate it EVERYTIME we make a Change in Styling. Whereas, the Second Command i.e. (with "--watch") will automatically update the "style.css" i.e. Output File for every change implicitly.
4. After running one of the above two commands, a "**style.css**" will be Generated that contains the css code Tailwind has written.
5. In "**index.html**" file, Link this File as Stylesheet, by Writing this in the Header Section:
    ```html
    <link rel="stylesheet" href="./style.css">
    ```
    > Where "href" is given the Value as Address of the "style.css" File.

# 