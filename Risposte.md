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


*Snack 3*
Code Question 3
const hamburger = { 
    name: "Cheese Burger", 
    weight: 250,
    maker: {
        name: "Anonymous Chef",
        restaurant: {
            name: "Hyur's Burgers",
            address: "Main Street, 123",
            isOpen: true,
        },
        age: 29
    }
};
​
const secondBurger = structuredClone(hamburger);
const thirdBurger = structuredClone(hamburger);
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice?

Risposta: 
All'inizio abbiamo un oggetto chiamato hamburger, che contiene al suo interno altri due oggetti: maker e, dentro di questo, restaurant. Quindi, in memoria esistono 3 oggetti.

Poi usiamo structuredClone(hamburger) per creare secondBurger e thirdBurger. Dato che questo metodo fa una copia completa e separata dell'oggetto, vengono creati altri 3 oggetti per ogni copia.

Alla fine, abbiamo:

3 oggetti dell'originale (hamburger, maker, restaurant)
3 oggetti per secondBurger
3 oggetti per thirdBurger
Totale: 9 oggetti in memoria.


*Snack 4*
Code Question 4
const chef = {
    name: "Chef Hyur",
    age: 29,
    makeBurger: (num = 1) => {
        console.log(`Ecco ${num} hamburger per te!`);
    },
}
​
const restaurant = {
    name: "Hyur's Burgers",
    address: {
        street: 'Main Street',
        number: 123,
    },
    openingDate: new Date(2025, 3, 11),
    isOpen: false,
};
Qual è il metodo migliore per clonare l’oggetto chef, e perché?
Qual è il metodo migliore per clonare l’oggetto restaurant, e perché?


Risposta: 
per clonara l'oggetto chef il metodo migliore è il metodo Spread, perchè al suo interno abbiamo una funzione e questo metodo ci permette di copiare le funzioni

mentre per l'oggetto restaurant il metodo migliore è structuredClone(), perchè essendo presente new date al suo interno che è un oggetto complesso, ci permette di copiarlo sotto forma di oggetto. 


*Snack 5 (Bonus)*

Code Question 5 (Bonus)
const hamburger = { 
    name: "Cheese Burger", 
    weight: 250,
    maker: {
        name: "Anonymous Chef",
        restaurant: {
            name: "Hyur's Burgers",
            address: "Main Street, 123",
            isOpen: true,
        },
        age: 29
    }
};
​
const newRestaurant = {...hamburger.maker.restaurant};
newRestaurant.name = "Hyur's II";
newRestaurant.address = "Second Street, 12";
const secondBurger = {...hamburger};
secondBurger.maker.restaurant = newRestaurant;
secondBurger.maker.name = "Chef Hyur";
​
console.log(hamburger.maker.name); // ?
console.log(secondBurger.maker.name); // ?
console.log(hamburger.maker.restaurant.name); // ?
console.log(secondBurger.maker.restaurant.name); // ?
Senza lanciare il codice, riesci a prevedere cosa viene stampato in console?
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice?

Risposte:
console.log(hamburger.maker.name); => "Chef Hyur" 
console.log(secondBurger.maker.name); => "Chef Hyur"
console.log(hamburger.maker.restaurant.name); => "Hyur's Burgers" 
console.log(secondBurger.maker.restaurant.name); => "Hyur's II" 

L'oggetto originale hamburger (contiene maker e restaurant) => 1 oggetto principale + 2 oggetti interni = 3 oggetti
L'oggetto newRestaurant => 1 nuovo oggetto
L'oggetto secondBurger (ma maker rimane lo stesso riferimento) => 1 nuovo oggetto
Totale: 5 oggetti creati in memoria.
