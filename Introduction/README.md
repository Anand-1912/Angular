**What is a Angular?**

1. Angular is a JavaScript framework for building Single Page Applications (SPA).

2. A framework is like a platform for developing software applications.

3. A framework can have pre-defined classes and functions that can be reused to add several functionalities , which otherwise we would have to write from scratch by our own.

4. for example, Angular provides required Classes and Methods to make a http call from the Client to Server. These functionalities are already tested and we can use them in our application.

5. So, A framework is a collection of predefined classes and methods which provides APIs for performing different operations when used in application.

What is Single Page Application **( SPA )**?

In a Single Page Application, only one HTML page will be loaded and when we navigate around the application, the html content of the page will be modified.

_Advantages_

1. Since we are using Javascript to change the content of the page, it is much faster. Here we are not reaching out to the server to request a new piece of HTML data, every time we navigate to a different URL.

2. When data is required from Server, it will be fetched in the background by Angular and it keeps the app responsive.

3. This allows us to create an application which is fast and reactive.

_Limitations of Plain Javascript and jQuery_

1. Hard to test
2. Hard to maintain
3. There are some functionalities which we will have to write from scratch when using Javascript / jQuery.

_Advantages of using Angular_

1. Testable
2. Lots of utility code
3. Applications developed using Angular are clean and lossely coupled. Easy to understand and maintain

**Tools required**

1. Node (install from exe or choco package manager)

   `node --version`

2. Angular CLI (after installing node and npm). We are using npm to install Angular.

   `npm install -global @angular/cli@latest`

   Angular CLI is a command line interface which we use to create **new angular projects** or generate some boiler plate code as well as create **deployable packages**.

3. Angular Version Check

   `ng version`

4. npm upgrade (if required)

   `npm install -g npm@latest`
