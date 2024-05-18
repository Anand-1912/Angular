1. To create a new Project in Angular

   `ng new <project_name>`

2. To create without a git repository (eg)

   `ng new angular-ekart --skip-git`

3. help

   `ng --help`

4. To serve the application.(run the ng serve command inside the project folder)

   `ng serve`

   what does it do?

   - It will compile the angular project
   - Generate the application bundles for js and css files and these bundles will be injected into index.html as scripts by the angular.

     - runtime.js
     - polyfills.js
     - main.js
     - vendor.js
     - styles.css

   - It will open the live development server on which the application will be running.

### Component

1. A Component in Angular consists of 5 main files

eg, if we have a component named 'app', then

- **app.component.ts** => Typescript file
- **app.component.html** => View template
- **app.component.css** => Style
- **app.component.spec.ts** => specs (for testing)
- **app.module.ts** => module (not available in standalone apps)
- **app.config.ts**

- _note_ : standalone apps wont have modules. To create an app with module, use the command `ng new <app-name> --no-standalone`

2. A component is represented using a TypeScript class

3. It is decorated with @Component decorator to which an Object is passed.

4. The object has the properties that identifies the selector, templateUrl and styleUrls.

```typescript
import { Component } from "@angular/core";
import { RouterOutlet } from "@angular/router";

@Component({
  selector: "app-root",
  standalone: true,
  imports: [RouterOutlet],
  templateUrl: "./app.component.html",
  styleUrl: "./app.component.css",
})
export class AppComponent {
  title = "angular-ekart";
}
```

5. Properties defined in the Component class can be accessed inside the template and rendered using **data binding**.

```html
<h1>Welcome to {{ title }}</h1>
```

### Folder Structure and Project Files

1. **node_modules**

- Contains Packages needed by Angular and the application
- Used only in local development environment
- Should not be checked in.
- The package.json and package-lock.json contains the dependency information.
- The Packages can be installed using **npm**

`npm install`
`npm ci` (for CI/CD Purposes)

2. **.editorconfig**

- Used to setup the team environment

eg,

```
[*.ts]
quote_type = single

```

3. **.gitignore**

- Contains the list of files and folder that should not be checked in

4. **angular.json**

- Contains the Configuration of Project !

5. **package.json**

- Contains the application and dev node package dependencies

6. **package-lock.json**

- Contains the **exact** (version) dependencies and sub dependencies that are required by project.
- Used in CI/CD
- Used by `npm ci`

7. **tsconfig.json**

- Contains settings for TypeScript compiler.
- The TypeScript uses these settings to compile the TypeScript to Javascript which can be understood by the browser.

8. **src**

- Where dev spends time a lot 😊
- Contains the Application code like Component, Service class, Modules, etc.
- An Angular Project can have many Applications.
- Each application will have a folder inside the src. (eg. App)
- Inside the application, we will have files for components and modules.
- Every Angular application in an Angular Project must have atleast one Component and Module.

9. **assets**

- We store the static assets eg. icons, images, text files
- These are publicly accessible

  eg. localhost:4200/assets/some_image.jpg

10. **index.html**

- The main html file of the application
- It will not by default has any script and style references
- All the scripts will be injected into it by Angular during the build process

11. **main.ts**

- starting point of the angular application
- bootstraps the app module.

```typescript
import { bootstrapApplication } from "@angular/platform-browser";
import { appConfig } from "./app/app.config";
import { AppComponent } from "./app/app.component";

bootstrapApplication(AppComponent, appConfig).catch((err) =>
  console.error(err)
);
```

12. **styles.css**

- Global style sheet used by the Angular Project
- Used by all the Components and Directives

### Bootstrapping

- Bootstrapping is the process of loading or initializing the Angular application.

- `ng serve`

  - When we use this command, the Angular CLI compiles the application, stores the compiled files in memory and directly starts it.
  - If we make any changes to our Angular App, Angular CLI will recompile and update the file. (kind of nodemon)

- `ng build`

  - Builds the Angular Project
  - We can see the compiled files in the **dist** folder.
  - `runtime.js` is the webpack runtime file
  - `polyfills.js` helps older browsers in executing modern JavaScript
  - `main.js` contains the application code. it contains the Javascript code compiled from typescript
  - `vendor.js` contains the scripts from Angular Core library and other 3rd Party libraries that we are using in Angular application.
  - `styles.js` - the styles.css files will be bundled as a Javascript file and injected into index.html

  - Angular CLI uses **Webpack** to traverse through our Angular App and it bundles JS and other files into one or more bundles. Angular itself sets the Configuration options for Webpack to work correctly.

  - Refer the Bootstrap diagram for the flow.

## Queries

1. Where the build, serve etc scripts are located?

2. How additional node modules are installed when they are not explicitly mentioned in the package.json?
   They are dependencies of dependices

3. What are Modules in Modern Javascript?

4. Webpack runtime?

5. What is bundling?

6. What is Webpack bundling?
