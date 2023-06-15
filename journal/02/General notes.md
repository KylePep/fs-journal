
<!-- STUB -->
<!-- SECTION ANIMAL MURDER MYSTERY -->
math.random() ----return a number 0-1 ex .57
math.floor() ----- round up or down
let randomArrayPosition = math.floor(Math.random * array.length) ------------is how you can access a random position of the array

<!-- SECTION assign guilty -->
function makeAMurderer(){
  let randomNumber = Math.random ------ a class called math, math.random returns a random number
  --------------------------------------This returns a huge span of random numbers from 0-1
}

function makeAMurderer(){
  let randomNumber = Math.random * 10 --- this will return 0-9 etc a number from 0-1*10
}

function makeAMurderer(){  ----------------------------------This function will return a random animal within the array
  let randomNumber = math.floor(Math.random * array.length)
  let randomAnimal = animals[randomNumber]
  randomAnimal.guilty = true;
}

<!-- SECTION find murderer -->
function findMurderer() {
  let foundAnimal = animals.find(animal => animal.guilty == true)
}

<!-- SECTION draw lineup -->
function drawAnimals() {
    let animalString = ''
  animals.forEach(animal => {
    animalString += animal.emoji
  })
  const animalLineupElement =  document.getElementbyId('animalLineup')
}

<!-- SECTION find mammals -->
function drawMammals(){
  let mammals = animals.filter(animal => animal.mammal)  ---- creating a new array that has only mammals inside

}

<!-- SECTION accuse -->
function accuseAnimal(){
  const accusedAnimal = window.prompt("WHO DUNNIT")
  
  let murderer = findMurderer()
  if (murderer.emoji == accusedAnimal){
    window.alert(You did it)
  } else {
    window.alert(You didnt do it)
    getClue()
  }
}

<!-- SECTION  Get murderer clue -->
function getClue(){
  let murderer = findMurderer()
  const clueElement = document.getElementById('clues')

  if(murderer.mammal){
    clueElement.innerHTML =  '<p> The animal is a mammal</p>'
    }
}

<!-- SECTION filter meat eaters --> ---------------- .includes lets you search through the array within the object
function filterMeatEaters(){
  let meatEaters = animals.filter(animal => animal.diet.includes('meats'))
  drawAnimals(meatEaters)
}

<!-- STUB -->

<!-- SECTION PASTAS -->

------Adding selected menu items to html elements

<!-- NOTE auto scroll with in an element //really tall column -->
------------Auto scroll portion of the site
max-height: xyzvh
overflow-y  auto

<Ul id= "cart"> -------------Unordered list
<li><li> -----------List item
</ul>

function drawcart(){

  let stringOfMenuItemHTML = ''

  let cartItems= menu.forEach(menuItem => {
    if(menuItem.quantity > 0){
      stringOfMenuItemHTML += `
        li  
          div class etc
            span ${menuItem.name} x${menuItem.quantity} span
            span ${menuItem.price.toFixed(2)} span
          div
        li
      `

    })

  const cartElement = document.getElementById('cart')
  cartElement.innHTML = stringOfMenuItemHTML

  <!-- NOTE /*html*/ --> is a text decorator that makes the text look like html
  cartElement.innerHtml = /*html*/'
        -----html element----
        div
          p
            words
          p
        div
  '
}

function drawTotal() {
  let cartTOtalElement = document.getElementById('cartTotal')

  let cartSum = 0

  menu.forEach(menuItem => {
    cartSum += (menuItem.price * menuItem.quantity)
  })

  cartTOtalElement.innerText = cartSum.toFixed(2).toString()
}

function checkOut(){
  const wantsToCheckOut = window.confirm("yes,checkout?")

  if (!wantsToCheckOut) {
    return
  } else {
    menu.forEach(menuItem => menuItem.quantity = 0)
  }
  drawCart()
}

<!-- SECTION ZOO KEEPER -->
<!-- 
  Game has moving elements that bounce within a box
  Game has a step system that -- happiness over time (5sec)
  There are mulitple elements
  system evaluates average happiness and returns a ranked paycheck
 -->
 setting flex to column and space between
 flex-grow will have the element take up all of the remaining flex space -- on the middle element--

user-select: none; ---------this will disable selection to the class or element it is called to in css

 .class > element {} -----------This will select the first child element underneath the element with the given class
 .class:hover --------------This will enable css to do specific things on hover
    cursor: crosshair; ----------- will change the cursor to crosshair on hover

    creating array of objects
    const array = [
      {
        name: 'batman',   ---------------important that an objects properties are seperated by commas
        emoji: '🦇',
        hunger: 100,
        isAlive: true
      }
      {
        name: 'robin, 
        emoji: '🐦',
        hunger: 40,
        isAlive: true
      }
    ]

  let animalElem = document.getElementById('batman')
  let animalParagraph = animalElem.querySelector('p') ------- This will return the p tags withinn the element with Id ='batman'
  let animalParagraph = animalElem.querySelector('p > span') ------- This will return the first span within a p tag inside Id = 'batman'