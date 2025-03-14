# 🚀 Angular Interview Cheat Sheet 🚀

### **1. What is Angular?**
- Angular is a TypeScript-based front-end framework developed by Google.
- It is used for building dynamic, scalable, and single-page web applications (SPAs).
- It follows the component-based architecture, promoting reusability and maintainability.
- Uses two-way data binding, dependency injection (DI), and directives to enhance functionality.
- Supports modular development with NgModules and lazy loading for performance optimization.
- Commonly used for large scale enterprise applications due to its robust ecosystem and tooling support.

### **2. Main features of Angular:**
- Modular architecture with reusable components.
- Two-way data binding synchronizing model and view.
- Dependency Injection (DI) for improved modularity and maintainability.
- Directives, Pipes, Routing, Lazy Loading, and State Management (NgRx).
- Comprehensive testing tools like Jasmine and Karma.

### **3. What are the files created with Angular application?**
1. `package.json`- All the packages required for the application. It includes -
  - **scripts** - How to run, build, test the application.
  - **dependencies** - Packages that goes into production build.
  - **devDependencies** - Packages only used during development.
2. `angular.json`- Contains all configurations of the app. Information about workspaces and applications in it.
3. `karma.conf.json`-  Configuration for unit testing with Karma. It uses Karma to run all tests and jasmine to write all tests.
4. `browserlist` - List of all supporting browsers.
5. `node_modules` - Includes all the packages installed.
6. `tsconfig.json` - TypeScript configuration file. Specifies TypeScript compilation rules and target environments.
7. `src` - Contains all source code of the Angular app.
8. `app` – Main application logic.  It includes -
  - `app.module.ts` – Root module where components, services, and modules are registered.
  - `app.component.ts` – Root component (entry point for the UI).
  - `app.component.html` – Template (HTML structure) of the main component.
  - `app.component.scss` – Styles for the main component.
9. `test.ts` - Loads all spec files recursively for karma.conf.js
10. `styles.css` - Global css file for global styles.
11. `polyfills.ts` - Makes the code backward compatible with older versions of JavaScript.
12. `main.ts` - Entry point, execution of the application starts here.
13. `index.html` - Main html served to user.
14. `favicon.io` - Application icon displayed in browser tab.
15. `assets` - Stores static files like images, icons, and JSON data.
16. `environments` – Environment configurations.
  - `environment.ts` – Development settings.
  - `environment.prod.ts` – Production settings.

### **4. What is template syntax in angular?**
- Template syntax defines how Angular interacts with the DOM and components.
- It includes directives, interpolation, property/event binding, pipes, and structural elements.

### **5. What is binding syntax in angular?**
- Binding syntax is used to connect data between the component and the template.
- There are four types:
 1. **Interpolation (`{{}}`)**:
  - Used to bind component properties inside the template.
```html
<p>Hello, {{ username }}!</p>
```
 2. **Property Binding (`[property]`)**:
- Binds a DOM property to a component property.
```html
<input [value]="userInput">
```
3. **Event Binding (`(event)`)**:
- Listens for user events and executes a component method.
```html
<button (click)="onSubmit()">Submit</button>
```
 4. **Two-Way Binding (`[()]`)**:
- Combines property binding and event binding for real-time data synchronization.
```html
<input [(ngModel)]="name"> 
```

### **6. What are Directives?**
- Directives are special instructions in Angular that extend HTML functionality.
- They help in manipulating the DOM by adding behavior to elements.
- Angular has four types of directives:
1. **Component Directives**:
- Components are a type of directive with a template.
- Defined using @Component() decorator.
```javascript
@Component({
  selector: 'app-example',
  template: '<h1>Hello Angular</h1>'
})
export class ExampleComponent {}
```
2. **Structural Directives**:
- Modify the structure of the DOM (add/remove elements dynamically).
- Example directives: 
   - **ngIf**: Doesn't display in DOM if condition isn't met.
   - **ngFor**: Used for binding arrays. Re-renders all data if anything changes.
   - **ngSwitch**: Uses ngSwitchCase for matching cases and ngSwitchDefault for a fallback option.
```html
<p *ngIf="isVisible">This text appears if isVisible is true.</p>
<ul>
  <li *ngFor="let item of items">{{ item }}</li>
</ul>
```
3. **Attribute Directives**:
- Modify the appearance or behavior of an element.
- Example directives: [ngClass], [ngStyle], custom directive.
```html
<p [ngClass]="{ 'highlight': isActive }">Styled text</p>
<p [ngStyle]="{ 'color': 'blue' }">Blue text</p>
```
4. **Custom Attribute Directive**:
- Can add custom behavior to an element.
```javascript
@Directive({ selector: '[appHighlight]' })
export class HighlightDirective {
  constructor(private el: ElementRef) {
    el.nativeElement.style.backgroundColor = 'yellow';
  }
}
```

### **7. What are Pipes?**
- Pipes are used to transform data before displaying it in the template.
- They help format values like text, dates, currency, percentages, etc.
- Pipes are applied using the | (pipe) operator.
1. Built-In pipes: uppercase, lowercase, date, currency, percent, json, async.
```html 
<p>{{ name | uppercase }}</p> <!-- Converts to uppercase -->
<p>{{ amount | currency:'USD' }}</p> <!-- Formats as USD currency -->
<p>{{ today | date:'longDate' }}</p> <!-- Formats as long date -->
```
2. Custom pipes: Custom pipes can be created using `@Pipe` decorator.
```javascript
@Pipe({ name: 'square' })
export class SquarePipe implements PipeTransform {
  transform(value: number): number {
    return value * value;
  }
}
```

### **8. What are Lifecycle Hooks?**
- Lifecycle Hooks are special functions that Angular calls at different stages of a component’s lifecycle.
- Lifecycle ends when component is destroyed.
- Major Lifecycle Hooks:
1. **ngOnInit()** – Called once after component initialization. Used for fetching data.
2. **ngOnChanges()** – Called when input properties change. Used for reacting to property updates.
3. **ngDoCheck()** – Called during every change detection cycle. Used for custom change detection.
4. **ngAfterContentInit()** – Called after content is projected into the component.
5. **ngAfterContentChecked()** – Called after projected content is checked.
6. **ngAfterViewInit()** – Called after component view (child components) is initialized.
7. **ngAfterViewChecked()** – Called after the component’s view is checked.
8. **ngOnDestroy()** – Called before the component is destroyed. Used for cleanup.

### **9. What is Dependency Injection?**
- Dependency Injection (DI) is a design pattern where dependencies (services) are provided to components instead of being created inside them.

### **10. What is Change detection in angular?**
- Change Detection updates the DOM when data changes.
- **Default Strategy**: Angular checks the entire component tree.
- **OnPush Strategy**: Optimizes performance by only checking when input properties change.

### **11. What are Services in angular?**
- Services in Angular are used to share data, logic, and functionality across multiple components.
- They help in code reusability, separation of concerns, and dependency injection.
- Services are created using the @Injectable() decorator.
- Service:
```javascript
@Injectable({ providedIn: 'root' })
export class DataService {
  getData() { return ['Angular', 'React']; }
```
- Component: 
```javascript
constructor(private dataService: DataService) {}
```

### **12. How do components interact in angular?**
- In Angular, components communicate and share data using the following methods:
1. **Parent to Child Communication** – @Input()
- The parent component passes data to the child component using property binding.
```javascript
@Component({ selector: 'app-child', template: '<p>{{ data }}</p>' })
export class ChildComponent {
  @Input() data: string;
}
```
```html
<app-child [data]="parentData"></app-child>
```
2. **Child to Parent Communication** – @Output() & EventEmitter
- The child component emits events to send data back to the parent.
```javascript
@Component({ selector: 'app-child', template: '<button (click)="sendMessage()">Click</button>' })
export class ChildComponent {
  @Output() message = new EventEmitter<string>();
  sendMessage() {
    this.message.emit('Hello Parent!');
  }
}
```
```html
<app-child (message)="receiveMessage($event)"></app-child>
```
3. **Sibling Communication** – Shared Service
- A service can store and share data between unrelated components.
```javascript
@Injectable({ providedIn: 'root' })
export class DataService {
  private data = new BehaviorSubject<string>('Initial Data');
  data$ = this.data.asObservable();
  updateData(value: string) { this.data.next(value); }
}
```
```javascript
constructor(private dataService: DataService) {}
this.dataService.updateData('New Data');
```
4. **Using Local Storage / State Management**
- For global data sharing, local storage, session storage, or state management (NgRx, Akita, NGXS) can be used.

### **13. What are Providers?**
- Providers define how Angular creates instances of services and makes them available for dependency injection.
- Providers are configured using providedIn or in the providers array of an @NgModule, @Component, or @Directive.
- Types of Providers:
1. **Factory Providers** – Creates a service dynamically using a factory function.
2. **Class Providers** – Uses a class to provide a service.
3. **Value Providers** – Supplies a fixed value instead of a service instance.

### **14. What is the difference between providedIn `root` and `any`?**
- The key differences are:

| Feature         | `providedIn: 'root'`        | `providedIn: 'any'`                    |
|---------------|--------------------------|----------------------------------|
| **Scope**      | Available globally       | Instantiated per lazy-loaded module |
| **Instantiation** | Single instance (singleton) | Multiple instances in different modules |
| **Use Case**   | Shared services (e.g., Auth, API) | Module-specific logic |

### **15. What is HttpClient in Angular?**
- Angular provides HttpClient for making HTTP requests to APIs.
- It is part of HttpClientModule, which must be imported in app.module.ts.
- It uses RxJS library internally.
- Supports GET, POST, PUT, DELETE, PATCH operations.

### **16. What is HttpInterceptor?**
- An HTTP Interceptor is a middleware that modifies HTTP requests and responses globally before they reach the server or client.
- Useful for adding authentication tokens, logging, modifying headers, or handling errors.
- Does not modify original request or response directly. Instead, they clone the request or response and modify the cloned copy.

### **17. What is APP_INITIALIZER?**
- APP_INITIALIZER is an Angular factory function that runs before the app initializes.
- Useful for preloading configuration settings, fetching user preferences, or initializing global services.

### **18. What is Angular router?**
- The Angular Router is a built-in module that enables navigation between different views (components) in a Single Page Application (SPA).
- It updates the browser URL and dynamically loads the corresponding component without reloading the page.

### **19. What are the different types of forms in angular?**
-  Used to capture and manage user input efficiently. Angular provides two types of forms:
1. **Template-Driven Forms**: 
- Uses directives in the HTML template (ngModel) for form binding.
- Best for simple forms with minimal logic.
- Requires importing FormsModule.
```html
<form #userForm="ngForm" (ngSubmit)="onSubmit(userForm)">
  <input type="text" name="username" ngModel required />
  <button type="submit">Submit</button>
</form>
```
2. **Reactive Forms**:
- Uses FormControl and FormGroup to manage form state in TypeScript.
- Best for complex forms with dynamic validation and conditional fields.
- Requires importing ReactiveFormsModule.
```javascript
this.userForm = new FormGroup({
  username: new FormControl('', Validators.required),
  email: new FormControl('', [Validators.required, Validators.email])
});
```
```html
<form [formGroup]="userForm" (ngSubmit)="onSubmit()">
  <input type="text" formControlName="username" />
  <button type="submit">Submit</button>
</form>
```

### **20. What are Modules in angular?**
- Modules in Angular help organize the application into reusable and manageable units.
- Encapsulate Components, Directives, Pipes, and Services.
- Supports lazy loading to improve performance.
- Use imports, exports, and providers to share dependencies.

### **21. What is Ahead-of-time compilation?**
- AOT Compilation converts Angular HTML & TypeScript into optimized JavaScript at build time (before browser execution).
- Improves performance, security, and faster rendering.

### **22. How do the forRoot() and forChild() methods help in Angular module configuration?**
- `forRoot()` is used in the root module to configure singleton services.
- `forChild()` is used in feature modules to configure routes and child dependencies.

### **23. What is HttpClientHandler, Interceptors, and what are their practical uses?**
- `HttpClientHandler` processes HTTP requests and responses.
- Interceptors modify requests and responses globally (e.g., authentication, logging, error handling).
- Used for token injection, request transformation, and API monitoring.

### **24. How does Angular's HTTP client handle request retrying?**
- RxJS `retry()` operator is used to reattempt failed HTTP requests.
- Helps in handling transient network failures and improving app resilience.

### **25. What is the significance of NgRx in Angular applications?**
- Implements Redux pattern for state management.
- Provides a unidirectional data flow with actions, reducers, effects, and selectors.
- Useful for large-scale applications requiring centralized state management.

### **26. What is the significance of NgRx Store in Angular applications?**
- Maintains application state in an immutable, observable manner.
- Improves state predictability, debugging, and separation of concerns.

### **27. How does Angular's change detection work and what are its architectural advantages?**
- Uses Zone.js to track asynchronous operations and update the view.
- Supports `OnPush` strategy to optimize performance by detecting immutable data changes.

### **28. Can you explain the concept of lazy loading in Angular and its benefits?**
- Loads feature modules only when needed, reducing the initial bundle size.
- Improves performance and faster initial loading time.

### **29. How does Angular handle form validation? Differences between reactive and template-driven forms?**
- Template-driven forms use directives (`ngModel`) and are simple but less scalable.
- Reactive forms use `FormControl`, `FormGroup`, and `FormBuilder`, offering better control.
- Supports built-in and custom validators.

### **30. What is the role of testing in Angular applications and key testing strategies?**
- Unit testing with Jasmine and Karma for component logic.
- Integration testing for verifying multiple components working together.
- End-to-End (E2E) testing with Protractor or Cypress.

### **31. What is the purpose of TestBed in Angular testing?**
- Used to configure and initialize components in test cases.
- Mocks dependencies for isolated testing of Angular elements.

### **32. What is a custom pipe and when would you use one?**
- A user-defined transformation function for template data.
- Used for complex formatting like date conversions or filtering arrays.

### **33. How is request caching implemented as an architectural constraint in RESTful services?**
- Uses HTTP caching headers (`ETag`, `Cache-Control`).
- Improves response times and reduces server load.

### **34. What is the concept of service workers in Angular and their role in building progressive web apps?**
- Service workers run in the background, enabling offline support and caching strategies.
- Used for push notifications, background sync, and performance improvements.

### **35. What are route guards in angular?**
- Route Guards in Angular control access to routes based on conditions.
- Implemented using CanActivate, CanDeactivate, CanLoad, Resolve, and CanActivateChild.
- They return true (allow navigation) or false (prevent navigation).

| Guard          | Purpose      |
|----------------|----------------------------|
| CanActivate	| Prevents unauthorized users from accessing a route.|
| CanDeactivate	| Warns users before leaving a page (e.g., unsaved changes). |
| CanLoad	| Restricts lazy-loaded module access based on conditions. |
| Resolve	| Pre-fetches data before activating a route. |
| CanActivateChild	| Applies CanActivate logic to child routes. |


### **36. Explain the difference between AngularJS and Angular?**

| Feature            | AngularJS (1.x)              | Angular (2+)                     |
|--------------------|----------------------------|----------------------------------|
| **Architecture**   | MVC (Model-View-Controller) | Component-based architecture    |
| **Language**       | JavaScript                 | TypeScript                      |
| **Data Binding**   | Two-way data binding       | Two-way & one-way data binding  |
| **Dependency Injection** | Limited support       | Powerful, hierarchical DI       |
| **Mobile Support** | Not optimized for mobile  | Designed for mobile-first apps  |
| **Performance**    | Slower due to digest cycle | Faster with AOT compilation & Ivy renderer |
| **Directives**     | `ng-model`, `ng-repeat`, etc. | `*ngFor`, `*ngIf`, custom directives |
| **Routing**        | `ngRoute` or `UI-Router`   | `@angular/router` module       |
| **Modules**        | No modular system         | Uses `NgModule` for modularity  |
| **DOM Handling**   | Manipulated directly      | Uses virtual DOM for efficiency |
| **Support & Updates** | Discontinued (no updates) | Actively maintained by Google  |

### **37. What is Default route and Wildcard route in angular?**
1. **Default Route `path: ''`**:
- Redirects users to a default component when they visit the base URL.
- Typically used to load the home page or a landing page.
- Implemented using the redirectTo property.
```javascript
const routes: Routes = [
  { path: '', redirectTo: 'home', pathMatch: 'full' }, // Default route
  { path: 'home', component: HomeComponent }
];
```
2. **Wildcard Route `path: '**'`**:
- Captures all undefined or invalid routes.
- Typically used to show a "Page Not Found" (404) component.
```javascript
const routes: Routes = [
  { path: 'dashboard', component: DashboardComponent },
  { path: '**', component: PageNotFoundComponent } // Wildcard route
];
```

### **38. What is Angular CLI?**
- Angular CLI (Command Line Interface) is a powerful tool that helps developers create, manage, and build Angular applications efficiently.
- It automates tasks like project setup, component creation, testing, and deployment.

| Feature	| Description |
|--------------------|----------------------------|
| Project Setup	| Quickly creates a new Angular app using ng new project-name. |
| Generate Files |	Generates components, services, modules, and more using ng generate. |
| Serve Application |	Runs a development server using ng serve. |
| Build & Optimize |	Builds the project for production using ng build --prod. |
| Testing	| Runs unit tests (ng test) and end-to-end tests (ng e2e). |
| Routing & Modules |	Automatically adds routing and modules with --routing and --module flags. |

### **39. How to Implement Lazy Loading in Angular?**
- Lazy loading delays module loading until it is needed, improving performance.
1. Create a feature module (Example: UserModule).
2. Use loadChildren in app-routing.module.ts:
```typescript
{ path: 'user', loadChildren: () => import('./user/user.module').then(m => m.UserModule) }
```
3. Remove UserModule from imports in AppModule.

### **40. What are Single Page Applications (SPAs)?**
- SPAs dynamically update content without reloading the page.
- Uses routing (RouterModule) to load components efficiently.
- Improves performance & user experience compared to traditional multi-page apps.

### **41. What is Angular CDK (Component Dev Kit)?**
- A lightweight toolkit for building reusable UI components without Angular Material.
- Features Include: Drag & Drop, Virtual Scrolling, Overlay, Accessibility (A11Y), Tree Structures.

### **42. What is Polyfills in Angular?**
- Polyfills are JavaScript scripts that provide modern features in older browsers that don’t support them.
- They mimic new JavaScript/HTML/CSS functionalities for older browsers like IE11.
- Angular includes a polyfills.ts file where necessary polyfills can be added.
- It contains ES6+, zone.js, and web API polyfills required for Angular to run in various browsers.
- If a browser doesn’t support a feature, it loads the polyfill as a fallback.
- Modern browsers ignore unnecessary polyfills to optimize performance.
- Enables features like Promises, Fetch API, and async/await in older browsers.

### **43. What is ng-template?**
- Defines a reusable HTML structure without rendering it immediately.

### **44. Difference between ngOnInit and constructor?**

|Feature |	constructor() |	ngOnInit() |
|-----------|-----------|-------------|
| Execution |	Runs when the class is instantiated |	Runs after component initialization |
| Purpose |	Used for dependency injection | 	Used for initialization logic |
| Access to Input Data	| No	| Yes |

### **45. What is Server-Side Rendering (SSR) in Angular?**
- Server-Side Rendering (SSR) is a technique where Angular applications are rendered on the server instead of the browser before sending the final HTML to the client.
- Angular normally runs as a Single Page Application (SPA) where the browser downloads JavaScript, processes it, and then renders the page.
- With SSR:
1. User Requests a Page → Browser sends a request to the server.
2. Server Generates Pre-Rendered HTML → The server processes the Angular components and sends the fully rendered HTML to the client.
3. Client Loads the Page → The browser displays the content instantly.
4. Angular Hydration (Reattaching Events & Logic) → The application becomes interactive once the JavaScript is loaded.
- Improves SEO, performance, and faster initial load time.
- Implemented using Angular Universal `(@angular/platform-server)`.

### **46. What is Zone.js in Angular?**
- Zone.js is a JavaScript library used by Angular for change detection. It modifies browser APIs like setTimeout, event listeners, and promises to detect asynchronous operations and trigger UI updates automatically.
- Tracks tasks like HTTP requests, timers, and user interactions.
- Notifies Angular when something changes, updating the UI without manually calling `ChangeDetectorRef.detectChanges()`.

### **47. What Are Decorators in Angular?**
- Decorators in Angular are special functions that enhance classes, methods, properties, and parameters by adding metadata. They are part of TypeScript and play a crucial role in Angular's architecture.
1. **Class Decorators** – Used to define Angular classes like components, directives, modules, and services. Example: `@Component(), @Directive(), @NgModule(), @Injectable()`
2. **Property Decorators** – Used to bind data to a class property.
Examples: `@Input(), @Output(), @HostBinding()`
3. **Method Decorators** – Modify or extend the behavior of class methods. Examples: `@HostListener()` (listens for events on the host element).
4. **Parameter Decorators** – Used inside constructors to inject dependencies. Example: `@Inject()`

### **48. What is Metadata in Angular Decorators?**
- Metadata in Angular provides information about a class, method, or property to Angular, helping it understand how to process the decorated element. 
- It is an object passed inside decorators like @Component(), @NgModule(), and @Injectable() that defines their behavior.
 Example: Metadata in @Component()
```typescript
@Component({
  selector: 'app-hello', // Defines the custom HTML tag for component
  template: '<h1>Hello, {{name}}</h1>', // Specifies the HTML structure
  styles: ['h1 { color: blue; }'] // Adds CSS styling
})
```

### **49. What is @NgModule in Angular?**
- @NgModule is a decorator that defines an Angular module, which is a container for components, directives, services, and other modules. It helps in structuring and organizing the application.

### **50. What is a Module in Angular?**
- A module in Angular is a container that organizes related components, directives, services, and pipes into a functional unit.
Types of Modules in Angular -
1. **Root Module (AppModule)** – The main entry point of an Angular application.
2. **Feature Modules** – Manages specific features.
3. **Shared Modules** – Contains reusable components, directives, and pipes.
4. **Core Module** – Stores singleton services (e.g., authentication, logging).


---
