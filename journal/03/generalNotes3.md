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

<!-- SECTION Modal -->