## Understanding Bundlers

Its a tools that packages our app so it can be shipped to production.

### Examples of Bundlers

- Webpack
- Parcel
- Vite

Note: When you hit the command, create-react-app, bundler used is parcel.

## Setting up a react project

### configuring project

npm init

- To use packages in our code, we need package manager.
- NPM: Node package managers.
- It will create a package.json file.

### package.json

- Package.json file is a configuration for NPM. Whatever
  packages our project needs, we install those packages using
  npm install <packageName>.

- Once package installation is complete, their versions and
  configuration related information is stored as dependencies
  inside package.json file.

### Installing parcel (our Bundler for React App)

- npm install -D parcel

- Now package-lock.json file is generated.

### package-lock.json

- Package-lock.json locks the exact version of packages being
  used in the project.

### package.json and package-lock-json differences

- In package. json we have information about generic version
  of installed packages whereas in package.lock.json we have
  information about the specific or exact version of
  installed packages.

### node_modules

- Database for NPM
- Every dependency in node_module will have its package.json.
- Every dependency in node_module will have its package.json.

NOTE: Never touch node_modules and package-lock.json

### Running app

npx parcel index.html

- npx means ‘execute using npm’
- index.html is the entry point

### Hot Module Replacement (HMR):

- It means that parcel will keep a track of all the files which
  you are updating.
- There is File Watcher Algorithm (written in C++). It keeps
  track of all the files which are changing realtime and it
  tells the server to reload.
- These are all done by PARCEL

### parcel-cache:

- Parcel caches code all the time.
- When we run the application, a build is created which take some time in ms.
- If we make any code changes and save the application, another build will be triggered,
  which might take even less time than the previous build.
- This reduction of time is due to parcel cache.
- Parcel immediately loads the code from cache every time there is a subsequent build.
- On the very first build, parcel creates a folder, .parcel-cache where it stores the caches in
  binary code format.
- Parcel gives faster build, faster development exprience because of caching.

### dist

- It keeps the file minified for us.
- When bundler builds the app, the build goes into a folder called dist.
- The `/dist` folder contains the minimized and optimized version of source code.
- Along with the minified code, the /dist folder also comprises of all complied modules that may
  not be used with other system.

- When we run command `npx parcel index.html`,

  - This is will create a faster development version of the project and serves it on server.

- We can command `npx parcel build index.html` to make a production build.
  - It creates a lot of things, minify our file.
  - Parcel will build all the production file to the dist folder.
