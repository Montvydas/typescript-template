# Minimal changes to run the template

1. Install all the dependencies:

    $ npm install

2. Run code watcher to look for changes on another terminal window:

    $ npm run build-watch

3. Run lite-server, which checks for code changes and then updates the everything in the browser [run] - optional:

    $ npm [run] start

Note: nodemon doesn't work with applications which have an "end". You would need expressjs, which would ensure that the app is alive all the time to work with nodemon.

---------------------------------------------------------------------------

# If interested to know how the structure was setup:

1. Initialise npm project:

    $ npm init

2. Install lite-server for dev purposes:

    $ npm i lite-server --save-dev

3. Initialised the whole project work with Ts (creates tsconfig.json):

    $ tsc --init

4. In the created tsconfig.json uncomment outDir and rootDir lines and structure project by adding src and dest folders. Add all .ts to src and remove .js from the project if such exist. Now adjust the config file:

    ...
        "target": "es6",
    ...
        "outDir": "./dest",
        "rootDir": "./src",
    ...

4. Modify package.json to add some useful scripts:

    "scripts": {
        ...
        "start": "lite-server",
        "build": "tsc",
        "build-watch": "tsc --watch"
    }

5. Created index.html file and a template inside by entering html5 in VS code and allowing to populate everything, then add reference to the script:

    <head>
        ...
        <script src="dest/app.js" defer></script>
    </head>

6. Created gitignore and added node_modules and dest folder.

7. (Optional) If needed you could add new entry "exclude" with paths to exclude when compiling e.g. (note this is done by default, don't need to exclide node_modules):

    {
      "compiler_options": {
      ...
      },
      "exclude": [
        "node_modules"
      ],
      "include": [
        "some_path"
      ]
    }
