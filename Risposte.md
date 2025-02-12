*Snack 1:*
Code Question 1
const hamburger = { name: "Cheese Burger", weight: 250 };
const secondBurger = hamburger;
secondBurger.name = 'Double Cheese Burger';
secondBurger.weight = 500;
​
console.log(hamburger.name); // ?
console.log(secondBurger.name ); // ?
Senza lanciare il codice, riesci a prevedere cosa viene stampato in console?
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice? */

 Risposta:
in console verrà stampato "Double Cheese Burger" ad entrambi perchè nella seconda variabile creata non vai a creare una copia dell'oggetto 
ma una copia dell'indirizzo all'oggetto quindi modificando la proprietà della "copia" si andrà a modificare l'oggetto originale.

Risposta 2:
è stato creato un solo oggetto in memoria.
