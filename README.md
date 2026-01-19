# Windows Setup Instructions

## Step 1

Install Chocolatey. 

Install instructions for Chocolatey can be found [Chocolatey](https://chocolatey.org/install)

## Step 2

After Chocolatey is installed run the following commands to install dependencies:

```
choco install -y nodejs-lts hugo git
npm i
npm install --save-dev cross-env
npm install --save-dev rimraf
```
## Step 3 

Open the project in your IDE of choice. 

Navigate to your ```/package.json``` file

Replace ```scripts: {}``` with this:

```
"scripts": {
    "clean": "rimraf public",
    "start": "cross-env TAILWIND_MODE=watch NODE_ENV=development npm-run-all clean prelim:twcss --parallel dev:*",
    "build": "NODE_ENV=production npm-run-all clean prelim:twcss prod:*",
    "prelim:twcss": "npx tailwindcss -i ./assets/css/main.css -o ./static/css/main.css --jit",
    "dev:twcssw": "npx tailwindcss -i ./assets/css/main.css -o ./static/css/main.css --jit -w",
    "dev:hugo": "hugo server",
    "prod:twcss": "./node_modules/tailwindcss/lib/cli.js -i ./assets/css/main.css -o ./static/css/main.css --jit --minify",
    "prod:hugo": "hugo --gc --minify"
  },
```
Save the changes.

## Step 4

Run ```npm run dev```

This will start up the project locally.
After about a minute or so you should see something like
```Running on localhost:1313```







This is a private repo. 

This is meant for testing and previewing code. 

Additional actions can be granted but must be given permission
