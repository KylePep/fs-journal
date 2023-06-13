

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