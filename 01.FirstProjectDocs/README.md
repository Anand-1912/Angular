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

- app.component.ts => Typescript file
- app.component.html => View template
- app.component.css => Style
- app.component.spec.ts => specs (for testing)
- app.compoent.module.ts => module

2. A component is represented using a TypeScript class

3. It is decorated with @Component decorated to which an Object is passed.

4. The object has the properties that identifies the Selector, templateUrl and styleUrls.

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

5. Properties defined inside the Components can be accessed inside the template and rendered using **data binding**.

```html
<h1>Welcome to {{ title }}</h1>
```

### Folder Structure and Project Files

1. node_modules

- Contains Packages needed by Angular and the application
- Used only in local development environment
- Should not be checked in.
- The package.json and package-lock.json contains the dependency information.
- The Packages can be installed using **npm**

`npm install`
`npm ci` (for CI/CD Purposes)

2. .editorconfig

- used to setup the team environment

eg,

```
[*.ts]
quote_type = single

```

3. .gitignore

- Contains the list of files and folder that should not be checked in

4. angular.json

- Contains the Configuration of Project !

5. package.json

- Contains the application and dev node package dependencies

6. package-lock.json

- contains the **exact** (version) dependencies and sub dependencies that are required by application.

- used in CI/CD

- used by npm ci

7. tsconfig

- contains settings for TypeScript compiler.
- The TypeScript uses these settings to compile the TypeScript to Javascript which can be understood by the browser.

8. src

- Where dev spends a lot 😊
- Contains the Application code like Component, Service class, Modules, etc.
- An Angular Project can have many Applications.
- Each application will have a folder inside the src. (eg. App)
- Inside the application, we will have files for components and modules.
- Every Angular application in a Angular Project must have atleast one Component and Module.

9. assets

- We store the static assets eg. icons, images, text files
- These are publicly accessible

  eg. localhost:4200/assets/some_image.jpg

10. index.html

- main html file of the application
- it will not by default has any script and style references
- All the scripts will be injected into it by Angular during the build process

11. main.ts

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

12. styles.css

- Global style sheet using by Angular Project
- used by all the Components and Directives

## Queries

1. where the build, serve etc scripts are located?

2. how additional node modules are installed when they are not explicitly mentioned in the package.json?
   They are dependencies of dependices
