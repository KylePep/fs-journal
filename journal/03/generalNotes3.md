<!-- Even more notes on mvc -->

Using the router today
router is an array of objects
the view is a path that injects a different set of HTML paired with its controller

.col-10 m-auto the margin auto put it in the center

<!-- SECTION new stuff -->

h tags and href= takes you to link, without the https you navigate views via the router

making a new view, add an object to the view array
            path: '#/cars'
          html 
            a tag href= '#/cars'---

Inside of car class
      constructor
            this.id = generateId()

 ---date class---
      this.listingDate = new Date() -----------------Pulls the entire date from the computer
              .toLocaleString() gets a pretty good looking date

      run a get within a get 
            get ComputeGrandmaBanner(){
              if (this.ownedByGrandma){
                return `
                div-div etc
                `
              }
              return ``
            }


Turinary operator

carData.ownedByGrandma = cardData.ownedByGrandma == 'on' ? true : false

using await
  make it async
  async deletCar(carId){

  }

Splice



<!-- ANCHOR Thursday notes -->

<!-- SECTION Redacted notes -->
Mic likes to start with a model, its contrustor fleshed out and  a simple getter to draw to the screen.

Turinary is a one line if statement

variable = (do we have that variable) ? (yes variable = that variable) : (no do something else)

Mic likes index => router => Controller => Service => AppState => Model
    This is reminicent of the flow of data

Take an string array and turn it into an list of words

          let arr = this.report.split(' ')  ----------split the string on 'space' character

get computedRedactedReport() {
          let mapped = arr.map(word => {
            if(_badwords.includes(word.toLowerCase())) {
              return '⬛⬛⬛'
            } return word
          })
          //return mapped -------------------This yields an array of strings
              return mapped.join(' ' ) ------------This yields an array of a single string
          }  

Build small forms, makes testing easier

... is a spread operator, this takes an array and removes the brackets essentially

let arr = [1,2,3]
console.log([...arr,4])---------this yields [1,2,3,4]
console.log([4,...arr])---------this yields [4,1,2,3]

init(){
  this.cases = loadState('cases',[Case]) -------------- The brackets on Case are necissary because when it gets saved to local storage it looses its class
                                        -----------------This lets you leave in your initialization information.
}

let newContent = document.getElementById('case-content').value
casesService.saveCase(newContent)
saveCase(newContent){
  const theCase = AppState.activeCase
  theCase.report = newContent

  _saveState()
}

inside of html moving away from an element is call onblur
    onblur= "app.CasesController.lockCase()"