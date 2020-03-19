# Requirements

![image](https://raw.githubusercontent.com/sergisergio/ANGULAR_Cours/master/Partie3.png)

[NODE.JS](https://nodejs.org/en/download/)

[NPM](https://docs.npmjs.com/)
``` bash
npm install -g npm@latest
```

[ANGULAR/CLI](https://cli.angular.io/)
``` bash
npm install -g @angular/cli
```

[DOC ANGULAR](https://angular.io/)
[DOC TYPESCRIPT](https://www.typescriptlang.org/docs/home.html)
[DOC IONIC](https://ionicframework.com/docs/)


## Create a project
``` bash
ng new mon-premier-projet
```
``` bash
cd mon-premier-projet
ng serve --open
```
Go to http://localhost:4200
Or try another port
``` bash
ng serve -o --port 4300
```

## Create a component
``` bash
ng generate component mycomponent
```

## Dynamic Data

***String Interpolation***  (from TS to HTML)
Declare a string variable in ts file, then pass it to html file with {{ }}.

***Property Binding***  (from TS to HTML)
Add a property in ts file, then pass it to a DOM element in html file (ex: [disabled]="!isAuth")

***Event Binding*** (from HTML to TS)
Add (click) in a button (ex: (click)="onAllumer") and declare this function in ts file.
[MDN Web Docs](https://developer.mozilla.org/fr/docs/Web/Guide/DOM/Events/Creating_and_triggering_events)
[W3Schools](https://www.w3schools.com/js/js_events.asp)

***Two-way binding*** (Propert Binding and Event Binding in the same time)

## Directives

- *ngIf="condition"
- *ngFor="let obj of myArray"
- *ngStyle (give styles to an object from Dom dynamically)
- *ngClass (add a CSS class dynamically)

## Pipes

Exemples:
- {{ lastUpdate | date }}
- {{ lastUpdate | date: 'short' }}
- {{ lastUpdate | date: 'yMMMMEEEEd' }}
- {{ lastUpdate | date: 'yMMMMEEEEd' | uppercase }}
- {{ lastUpdate | async | date: 'yMMMMEEEEd' | uppercase }}

## Services

- Create AppareilService et du service AuthService.
- In this application, we inject those services in AppModule, so that only one instance for a service is available in all others parts of our app (in "providers").
- To use a service in a component, we have to declare it as an argument in its constructor.
- ngOnInit is a "lifecycle hook". This method is executed once an instance when the component is created by Angular, and after its constructor.

![OC](https://user.oc-static.com/upload/2018/02/23/15194057472768_Screen%20Shot%202018-02-23%20at%2018.08.45.png)

## Routing

``` bash
ng g c auth
```
``` bash
ng g c appareil-view
```
Il faut déclarer les routes dans app.module.ts. On crée une constante de type Routes.
Une fois les routes créées, il faut les enregistrer dans l'application. Il faut importer RouterModule et l'ajouter à l'array "imports" de AppModule.
Maintenant il faut dire à Angular où on souhaite afficher les components dans le template quand l'utilisateur navigue vers la route en question grâce à la balise <router-outlet>
``` bash
<div class="container">
  <div class="row">
    <div class="col-xs-12">
      <router-outlet></router-outlet>
    </div>
  </div>
</div>
```
Pour la navigation, on utilise routerLink plutôt que href.

## Observing Data with RxJS

- Observable = object sending some informations whom we'd like to react to.
- With this observable, we link an observer (code which will be executed each time the Observable send an information).
- Subject = kind of Observable (can send inofrmation and can react to it).
- Operators = map(), filter(), throttleTime(), scan(), reduce().
See [ReactiveX](http://reactivex.io/)

## Forms - template method

- Create a form in the template: Angular analyse this form to understand the different inputs et make available its content.
- Add A submit type on the button and in form we add: <form (ngSubmit)="onSubmit(f)" #f="ngForm">.
- '#f' is a local reference.
- Then create a onSubmit() method in typescript.
- Don't forget to add the new route in AppModule and a routerLink in the menu.
- Then add an addAppareil in AppareilService to generate a new Appareil.
- Then we use this method in EditAppareilComponent (Router and AppareilService in its constructor).


## Forms - reactive method

- Create a form in TypeScript and also in the template and link both manually.


