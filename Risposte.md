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



*Snack 2*
Code Question 2
const hamburger = { 
    name: "Cheese Burger", 
    weight: 250,
    ingredients: ["Cheese", "Meat", "Bread", "Tomato"]
};
​
const secondBurger = {...hamburger};
secondBurger.ingredients[0] = "Salad";
​
console.log(hamburger.ingredients[0]); // ?
console.log(secondBurger.ingredients[0]); // ?
P.S.: Ricordati che gli Array, come gli oggetti, sono dei Reference Type (Tipi di Riferimento)!
Senza lanciare il codice, riesci a prevedere cosa viene stampato in console?
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice?


Risposta:
Verrà stampato "Salad" ad entrambi perchè gli array (come gli oggetti) non vengono copiati in profondità, ma solo il riferimento
perciò entrambi gli oggetti condividono lo stesso array in memoria. Essendo condiviso, quando si va a modificare ingredients di secondBurger si andrà a modificare anche ingredients di burger.

Risposta 2: sono stati creati 2 oggetti in memoria 