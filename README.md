# notes-foundations-1

title.textContent = banana['attributes']['name'];
title.textContent = banana.attributes.name;

description.textContent = banana.attributes['item-description'];




// 3. create an image tag and append to the `section` element
const img = document.createElement("img");
img.src = banana.attributes.image;
console.log(img);
const section = document.getElementById("section");
section.appendChild(img);

// 4. Loop through the stores and append an li with each store
const stores = banana.stores;  
const storesDom = document.getElementById('stores);

for (let i=0; i < stores.length; i++) {                         (or, banana.stores.length)
    console.log(banana.stores[i]);
}

OR

for(let blah of stores) {
    const li = document.createElement("li");
    li.textContent = store;
    storesDOM.appendChild(li);
    console.log(blah);
}




make a link to your products page
make a products folder
create index.html inside of it
./products

gonna be working on our products page
we want this to be a list of products
this is an e-commerce app, or an online fruit stand
a bunch of diff fruits i wanna display
hundred pieces of fruit
we want javas to do it for us

DATA MODELING!
data is in its own file called fruit.js, in its own folder called data


const apple = {
    id: 'apple',
    name: 'Red Apple'
    image: 'apple.png',
    description: 'A sweet, d34elicious, forbidden-to-some treat',
    category: 'tree-fruit',
    price: 1,
    cost: 0.25
};
figure out what info you wanna display for every product you have

we want an array of all our fruit objects

const fruits = [
    apple,
    banana,
    blueberry,
    cherry,
    greenApple,
    mango,
    orange
];

export default fruits;

HTML

<h1>Hello from Products!</h1>
<ul id="fruits">
    <li>
        <h3>Cherry</h3>
        <img src="./assets/cherry.png" alt="cherry image"/>
        <p class="description">July favorite</p>
        <p class="price">$4.00</p>
        <button>Add to Cart</button>
    </li>
</ul>

CSS

export function renderFruit('fruit') {
    const li = document.createElement('li');
    li.classList.add('tree-fruit');
    li.title = 'A sweet, delicious, forbidden-to-some treat';
    
    const h3 = document.createElement ('h3');
    h3.textContent = 'Red Apple';
    li.appendChild(h3);

    const img = document.createElement('img');
    img.src = '../assets/apple.png';
    img.alt = 'Red Apple image';
    li.appendChild(img)

    const p = document.createElement('p');
    p.textContent = '$1.00';
    
    const btn = document.createElement('button');
    btn.textContent = 'Add';
    btn.value = 'apple';
    p.appendChild(btn);

    li.appendChild(p);

    return li;
}


export function renderFruit(fruit) {
    const li = document.createElement('li');
    li.classList.add(fruit.category);
    li.title = fruit.description;
    
    const h3 = document.createElement ('h3');
    h3.textContent = fruit.name;
    li.appendChild(h3);

    const img = document.createElement('img');
    img.src = `../assets/${fruit.image}`;
    img.alt = `${fruit.name} image`;
    li.appendChild(img)

    const p = document.createElement('p');
    p.textContent = `$${fruit.price.toFixed(2)}`;
    
    const btn = document.createElement('button');
    btn.textContent = 'Add';
    btn.value = fruit.id;
    p.appendChild(btn);

    li.appendChild(p);

    return li;
}



IN PRODUCTS.JS

import { fruits } from '../data/fruits/js';
import { renderFruit } from './render-fruits.js';

const ul = document.getElementById('fruits');

// loop through each fruit in fruits
for (const fruit of fruits) {

// render the fruit using renderFruit function
    const el = renderFruits(fruit);
    console.log(el);

// append the rendered fruit to the <ul> element
    ul.appendChild(el);
}



