# Package-Json "Clean" Script Config Guide
Quick clean your dev installation with a "clean" script config integration into your package,json

### How to add "clean" function to a package json

Adding a clean script to your package.json
A "clean" script is a very common and useful tool in a development workflow for removing build artifacts, temporary files, or other generated content before a fresh build or installation.

Here's how to add one to your package.json file:

1. Locate the "scripts" section
Open your package.json file and find the "scripts" section. This is an object where you define custom scripts that can be run using the npm or yarn run command. 

2. Add the "clean" script
Add a new property to the scripts object with the name "clean". 

3. Define the command
The value of the "clean" script will be the command or set of commands that you want to execute when you run npm run clean. Here are a few common ways to define it: 

    Using rimraf (Recommended for cross-platform compatibility): This is a popular cross-platform package that works like rm -rf (for removing files and directories) and is generally preferred for broader compatibility (Windows, macOS, Linux).
        First, install rimraf as a dev dependency: npm install --save-dev rimraf.
        Then, add the script to your package.json:
        json

        {
          "name": "my-project",
          "version": "1.0.0",
          "scripts": {
            "clean": "rimraf dist build node_module" 
          },
          "devDependencies": {
            "rimraf": "^6.0.1" 
          }
        }

###
This example removes the dist, build and node_modules directories.
