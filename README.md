# Requirements

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



