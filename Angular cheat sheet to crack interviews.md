# Angular Developer Interview Questions Cheat Sheet

## 1. **Introduction to Angular**

- **What is Angular?**

  - A TypeScript-based open-source front-end framework maintained by Google.
  - Used to create single-page applications (SPAs) with modular architecture and dependency injection.
  - Provides declarative templates, component-based architecture, and extensive tooling.

- **Main features of Angular:**

  - Modular architecture with reusable components.
  - Two-way data binding synchronizing model and view.
  - Dependency Injection (DI) for improved modularity and maintainability.
  - Directives, Pipes, Routing, Lazy Loading, and State Management (NgRx).
  - Comprehensive testing tools like Jasmine and Karma.

- **How does an Angular application work?**

  - The `angular.json` file contains all configurations of the app.
  - The entry point is defined in `main.ts`, which bootstraps `AppModule`.
  - The `app.module.ts` file declares components, directives, and services.
  - The root component (`app.component.ts`) is rendered inside `index.html`.
  - Components have selectors, templates, and styles to manage UI behavior.

## 2. **Modules & Configuration**

- **How do the forRoot() and forChild() methods help in Angular module configuration?**
  - `forRoot()` is used in the root module to configure singleton services.
  - `forChild()` is used in feature modules to configure routes and child dependencies.

## 3. **Dependency Injection in Angular**

- **How can Angular's dependency injection system improve code maintainability and testability?**
  - Decouples dependencies, making components reusable and modular.
  - Enables easy mocking and replacement of services in tests.

## 4. **HTTP Client & API Communication**

- **What is HttpClientHandler, Interceptors, and what are their practical uses?**

  - `HttpClientHandler` processes HTTP requests and responses.
  - Interceptors modify requests and responses globally (e.g., authentication, logging, error handling).
  - Used for token injection, request transformation, and API monitoring.

- **How does Angular's HTTP client handle request retrying?**

  - RxJS `retry()` operator is used to reattempt failed HTTP requests.
  - Helps in handling transient network failures and improving app resilience.

## 5. **State Management**

- **What is the significance of NgRx in Angular applications?**

  - Implements Redux pattern for state management.
  - Provides a unidirectional data flow with actions, reducers, effects, and selectors.
  - Useful for large-scale applications requiring centralized state management.

- **What is the significance of NgRx Store in Angular applications?**

  - Maintains application state in an immutable, observable manner.
  - Improves state predictability, debugging, and separation of concerns.

## 6. **Change Detection & Performance Optimization**

- **How does Angular's change detection work and what are its architectural advantages?**

  - Uses Zone.js to track asynchronous operations and update the view.
  - Supports `OnPush` strategy to optimize performance by detecting immutable data changes.

- **Can you explain the concept of lazy loading in Angular and its benefits?**

  - Loads feature modules only when needed, reducing the initial bundle size.
  - Improves performance and faster initial loading time.

- **How does ahead-of-time (AOT) compilation improve Angular application performance?**

  - Compiles templates and TypeScript before runtime.
  - Reduces runtime overhead, enhances security, and speeds up rendering.

## 7. **Forms in Angular**

- **How does Angular handle form validation? Differences between reactive and template-driven forms?**
  - Template-driven forms use directives (`ngModel`) and are simple but less scalable.
  - Reactive forms use `FormControl`, `FormGroup`, and `FormBuilder`, offering better control.
  - Supports built-in and custom validators.

## 8. **Testing in Angular**

- **What is the role of testing in Angular applications and key testing strategies?**

  - Unit testing with Jasmine and Karma for component logic.
  - Integration testing for verifying multiple components working together.
  - End-to-End (E2E) testing with Protractor or Cypress.

- **What is the purpose of TestBed in Angular testing?**

  - Used to configure and initialize components in test cases.
  - Mocks dependencies for isolated testing of Angular elements.

## 9. **Pipes in Angular**

- **What is a custom pipe and when would you use one?**
  - A user-defined transformation function for template data.
  - Used for complex formatting like date conversions or filtering arrays.

## 10. **REST and API Handling**

- **How is request caching implemented as an architectural constraint in RESTful services?**
  - Uses HTTP caching headers (`ETag`, `Cache-Control`).
  - Improves response times and reduces server load.

## 11. **Application Scalability & Architecture**

- **How does Angular's model system support application scalability and modularity?**

  - Encourages component-based architecture for separation of concerns.
  - Supports lazy loading, modular services, and state management.

- **The architectural principles of microservices and their application in Angular projects?**

  - Microservices decompose an application into independent services.
  - Angular consumes microservices via REST APIs, enabling modular front-end development.

## 12. **Progressive Web Apps & Service Workers**

- **What is the concept of service workers in Angular and their role in building progressive web apps?**
  - Service workers run in the background, enabling offline support and caching strategies.
  - Used for push notifications, background sync, and performance improvements.

---
