
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
            span ${menuItem.quantity},${menuItem.name} span
            span ${menuItem.price * menuItem.quantity} span
          div
        li
      `

    }
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

