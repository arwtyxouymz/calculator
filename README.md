# calculator

This is a Vue.js implemented version of [this](https://github.com/florinpop17/app-ideas/blob/master/Projects/1-Beginner/Calculator-App.md).

[Here you can my calculator](https://arwtyxoumz-calculator.netlify.com/)

The default version is up ot 8digit, but you can input more numbers because my implemented version is support font scaling.

## User Stories

-   [x] User can see a display showing the current number entered or the
result of the last operation.
-   [x] User can see an entry pad containing buttons for the digits 0-9, 
operations - '+', '-', '/', and '=', a 'C' button (for clear), and an 'AC'
button (for clear all).
-   ~~[] User can enter numbers as sequences up to 8 digits long by clicking on
digits in the entry pad. Entry of any digits more than 8 will be ignored.~~
-   [x] User can click on an operation button to display the result of that
operation on:
    * the result of the preceding operation and the last number entered OR
    * the last two numbers entered OR
    * the last number entered
-   [x] User can click the 'C' button to clear the last number or the last
operation. If the users last entry was an operation the display will be
updated to the value that preceded it.
-   [x] User can click the 'AC' button to clear all internal work areas and
to set the display to 0.
-   ~~[] User can see 'ERR' displayed if any operation would exceed the 
8 digit maximum.~~

## Bonus features

-   [x] User can click a '+/-' button to change the sign of the number that is
currently displayed.
-   [x] User can see a decimal point ('.') button on the entry pad to that 
allows floating point numbers up to 3 places to be entered and operations to
be carried out to the maximum number of decimal places entered for any one
number.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
