# Angular Developer Interview Questions Cheat Sheet

## 1. **Basic Questions**
- **What is Angular?**  
  A TypeScript-based front-end framework for building web applications.
- **Angular vs AngularJS?**  
  Angular is TypeScript-based and component-driven; AngularJS is JavaScript-based and uses controllers.
- **Key features?**  
  Components, Directives, Modules, Routing, Dependency Injection.
- **Components vs Directives?**  
  Components have templates; directives modify DOM behavior.
- **Building blocks?**  
  Modules, Components, Templates, Metadata, Services, Dependency Injection.
- **Why TypeScript?**  
  Strong typing, better tooling, and improved maintainability.

## 2. **Angular Components & Modules**
- **What is a Component?**  
  A UI building block with HTML, CSS, and TypeScript.
- **What is a Module?**  
  A container for related components, directives, and services.
- **Lifecycle hooks?**  
  Methods like ngOnInit, ngOnDestroy for component lifecycle management.
- **Component communication?**  
  @Input(), @Output(), and services.
- **ViewEncapsulation?**  
  Controls component CSS scope (Emulated, ShadowDom, None).

## 3. **Directives & Pipes**
- **Structural vs Attribute Directives?**  
  Structural changes DOM (e.g., *ngIf); Attribute modifies elements (e.g., [ngClass]).
- **Custom Directive?**  
  Use @Directive() and apply logic to elements.
- **What is a Pipe?**  
  Transforms data in templates (e.g., date, currency).
- **Pure vs Impure Pipes?**  
  Pure pipes run only on input changes; impure pipes run on every change.
- **Built-in Pipes?**  
  date, currency, uppercase, lowercase, async.

## 4. **Services & Dependency Injection**
- **What is a Service?**  
  A reusable business logic provider.
- **Dependency Injection?**  
  A design pattern for injecting dependencies.
- **Ways to provide services?**  
  Root-level (providedIn: 'root') or module-level.
- **providedIn property?**  
  Determines service availability scope.

## 5. **Routing & Navigation**
- **What is Angular Router?**  
  Manages navigation between views.
- **Types of routing?**  
  Hash-based (# in URL) and Path-based.
- **Pass parameters in routing?**  
  Use route parameters or queryParams.
- **Lazy loading?**  
  Loads modules only when needed for performance.
- **Route Guards?**  
  Protect routes (AuthGuard, CanActivate, CanDeactivate).

## 6. **Forms in Angular**
- **Types of Forms?**  
  Template-driven and Reactive Forms.
- **Template vs Reactive Forms?**  
  Template-driven is simpler; Reactive offers more control.
- **Form validation?**  
  Built-in (required, minLength) and custom validators.
- **Handling form submission?**  
  Use ngSubmit for template-driven, subscribe for reactive.
- **FormGroup and FormControl?**  
  Manage reactive forms and controls.

## 7. **RxJS & Observables**
- **What is RxJS?**  
  A reactive programming library.
- **Observable?**  
  A stream of data that can be subscribed to.
- **Observable vs Promise?**  
  Observables are cancellable; Promises are not.
- **What are Subjects?**  
  Special observables that act as both observer and observable.
- **Common RxJS Operators?**  
  map, filter, switchMap, debounceTime.

## 8. **HTTP Client & API Communication**
- **How to make HTTP requests?**  
  Use HttpClientModule.
- **Common HTTP methods?**  
  GET, POST, PUT, DELETE.
- **Error handling?**  
  Use catchError in RxJS.
- **What is an Interceptor?**  
  Middleware for modifying HTTP requests/responses.
- **Authentication & Authorization?**  
  Use JWT or OAuth with HTTP Interceptor.

## 9. **State Management**
- **What is State Management?**  
  Managing application state centrally.
- **What is NgRx?**  
  A Redux-based state management library.
- **Actions, Reducers, Effects?**  
  Actions trigger state changes, Reducers handle state updates, Effects handle side effects.
- **NgRx vs BehaviorSubject?**  
  NgRx is scalable; BehaviorSubject is simple and local.
- **Other state management libraries?**  
  Akita, NGXS.

## 10. **Testing in Angular**
- **Types of testing?**  
  Unit, Integration, End-to-End (E2E).
- **What is Karma?**  
  A test runner for Angular.
- **What is Jasmine?**  
  A testing framework for Angular.
- **TestBed?**  
  Configures and initializes Angular components in tests.
- **Mocking dependencies?**  
  Use Jasmine spies or Angular testing utilities.

## 11. **Performance Optimization**
- **How to improve performance?**  
  Lazy loading, OnPush change detection, AOT.
- **What is Change Detection?**  
  Updates UI when data changes.
- **OnPush Strategy?**  
  Optimizes change detection using immutability.
- **Optimize large lists?**  
  Use trackBy in *ngFor.
- **Lazy loading benefits?**  
  Reduces initial load time.

## 12. **Security in Angular**
- **Common security risks?**  
  XSS, CSRF, injection attacks.
- **What is XSS?**  
  Injecting malicious scripts.
- **How does Angular prevent XSS?**  
  Automatic HTML sanitization.
- **What is CSP?**  
  Content Security Policy restricts script execution.
- **DomSanitizer?**  
  Bypasses Angular’s security mechanism when needed.

## 13. **Angular Build & Deployment**
- **Production build command?**  
  `ng build --prod`.
- **What is AOT?**  
  Ahead-of-Time compilation for faster rendering.
- **Environment management?**  
  Define multiple configurations in `angular.json`.
- **What is Angular Universal?**  
  Server-side rendering (SSR) for SEO.
- **Deployment?**  
  Upload `dist/` folder to a web server.

## 14. **Miscellaneous & Advanced Topics**
- **Angular CLI purpose?**  
  Automates project setup and management.
- **What are Web Components?**  
  Reusable UI elements across frameworks.
- **What is SSR?**  
  Server-Side Rendering improves SEO and performance.
- **How to handle memory leaks?**  
  Use unsubscribe and takeUntil.
- **What are hybrid apps?**  
  Apps using multiple front-end frameworks.

---
