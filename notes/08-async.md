# Async

Api is the middle man in the call and response of a user/browser to the back end server, in and out

Application Program Interface

API's are not standardized

<!-- NOTE -->
Install Extension JSON viewer
  -Json Javascript Object Notation-

make requests get responses

CRUD
Create Read Update Destroy 

Jeremy starts with a controller and a service to get the information from the API

Created controller relevant to the data hosted on API

<!-- NOTE Naming convention -->
  get-valueFromApiData-(

  )

  <!-- NOTE try catch -->
  async function () {
      try{  ---------try to do something
        await service.function()
        Pop.success(`${name} was supplied`)
    } catch (error){ ------------if fail, catch error do this
        console.error(error)
        Pop.error(error.message)
    }
  }

<!-- NOTE Fetch -->
    fetch is a built in function
    const response = fetch(url for Api)

<!-- STUB hard way -->
<!-- NOTE async get-->
async function(){-----------function is now asynchronous
  const response = await fetch() -------------Is now waiting for the fetch response before moving on.
  const jsonData = await response.json() ---- Response needs to be turned into json Data, Requires a 2nd await because it takes time to Json ify
}

<!-- STUB easy way-->
<!-- NOTE axios service -->

async get-xyz-(){
  const response = await -newName-.get('category/type')
}

axios script tag ----------this will be slacked out

create an AxiosService

export const -newName- = axios.create({
    baseUrl: 'something generic to the API'
    timeout: 8000
})


<!-- LOG the response from the Api every time -->

<!-- NOTE model -->
export class Model {
  consturctor(data){
    this.name = data.name
    ----you can rename variables
    this.locations = data.common_Locations || [] --- return empty array if the api has stuff = null sometimes
  }
}

const apimodelData = {
  Api object with different variables
}

<!-- NOTE AppState -->
apiModels = []


<!-- NOTE map -->

used to turn an array of pojo into an array of classes

const arrayOfApiModels = response.data.data.map(apiModelPojo => new Model(apiModelPojo))

AppState.apiModels = arrayOfApiModels

<!-- NOTE draw function with several awaits -->
    Use Appstate.on() --- there is no good way to trigger it otherwise


<!-- SECTION MVC Auth -->
-env.js ---- enviroment-
has fields to be filled by the webiste you are talking to 

<!-- NOTE Post -->
<!-- creating post -->

<!-- Controller -->
async creatCar(event){
  try {
    event.precentDefault()

    const form = event.target

    await carsService.createCar(CarData)

    const  CarData = getFormData(form)
  } catch (error) {
      error stuff
  }
}
<!-- Service -->
async createCar(carData){
  const res = await api.post('api/cars', carData )

  const newCar = new Care(res.datat)

  AppState.cars.push(newCar)
}

  <!-- NOTE Delete -->
  <!-- delete -->
  using a button with an onclick carrying its id

  computing the button using the account id will cause an error because the account returns late.
  You should have an or statement to prepare for this, then listen for the account to be updated and redraw the button

  constroller with an async and an await
    one for confirm and one for api resolve
      down to service

  <!-- service -->
  async deleteCar(carId) {

    const res = await api.delete(`api/cars/${carsId}`)

    const carIndex = AppState.cars.findIndex(c => c.id == cardId)

<!-- good to check for index so we dont try and delete the object at the end of the array -->
    if (carIndex == -1) {
      throw new Error(`No car index found with the id of ${carId}`)
    }

    AppState.cars.splic(carIndex, 1)
  }


  <!-- NOTE edit -->
  <!-- edit -->

    computing the button using the account id will cause an error because the account returns late.
  You should have an or statement to prepare for this, then listen for the account to be updated and redraw the button

  can prepare a getform with value on the input element
  button-editCar(event,${this.id})   ----event is from the service, this.id is because the form does not natively carry the id with it

  <!-- controller -->
    async and await down to service within a try catch
<!-- Service -->
  async editCar(carData, carId) {
    const res = await api.put()
  }


<!-- NOTE Static getter -->
<!-- like a getter but static? -->

Static methods are methods you can use with out needing to have an object from that class.
If you dont have any cars you wont be able to utilize cars.getXyz
but with static 

<!-- SECTION -->

Talking to two different Api's one to mostly get from and another to post to.
Take xyz information from the first one, change edit or save then post to the other api to save an accounts specific information

Starting from scratch-- be sure to set enviroment

<!-- NOTE env.js -->

Can be copied over from previous project.

<!-- NOTE appState -->
/** @type {object[]} */ --- this will do intellicense for a  regular array
spells = []

activeSpell = null

<!-- NOTE AxiosService -->

export const dndApi = axios.create({
  baseURL: 'https://ww.dnd5eapi.co'
  timeout: 8004
})

<!-- NOTE SpellsController -->

function _drawSpells(){
  template
  spells.forEach
        for each spell template += spell.name in a html element
              html element onclick="app.SpellsController.getSpellDetails('${spell.index}')"

    setHTML('spells-list',template)
}

function _drawActiveSpell(){
  let spell = AppState.activeSpell

}

create- add constructor- verify load {
  draw spells on update to AppState.spell
}

async getSpells(){
  try {
    await spellsService.getSpells()
    console.log('gotSpells')
  }catch {
    console.error(error)
    pop.error(error.message)
  }
}

async getSpellDetails(index){
  try {
    await spellsService.getSpellDetails(index)
    console.log('gotSpells')
  }catch {
    console.error(error)
    pop.error(error.message)
  }
}

<!-- NOTE SpellsService -->
class SpellsService{

async getSpells(){
  const res = await dndApi.get('api/spells')
  console.log('got spells',res.data)  ------------------------------ This is how you see what you actually got
  AppState.spells = res.data.results
}

async getSpellsDetails(spellIndex){
  const res = await dndApi.get(`api/spells/${spellIndex}`)
  console.log('got spell',res.data)  ------------------------------ This is how you see what you actually got
}

}
export const spellsService = new SpellsService()

<!-- NOTE Spell --model-- -->
export class Spell {
  constructor(){
    this.name = data.name
    this.description = data.desc
    this.range = data.range
    this.duration = data.duration
    <!-- this.damage = data.damage ? data.damage_type.name : 'Does no damge' -->
    this.damage = data.damage ? typeof(data.damge) == 'string' ? data.damge : data.damage.damage_type.name : 'Does no damage'
    this.level = data.level || 0
    this.material = data.material || 'No material needed'
    this.ritual = data.ritual
    this.concentration = data.concentration
    ETC
  }

get detailsTemplate(){
  ---template---
  With button at the bottom to post this to the api
}
}

<!-- NOTE SandboxSpellsController -->
create generic controller
  function to send the active spell down to the service

<!-- NOTE SandboxSpellsService -->


<!-- SECTION -->
in the axios service if an Api requires a key
within the export const{
  instead of withCredentials: true
  paramas: { api_key: ''}
}

<!-- NOTE bracket notation-->
instead of object.value.regular-image which wont work
object.value['regular-image']

<!-- NOTE changing style with js -->

function _drawPicture(){
  const picture = AppState.picture

  const htmlBody = document.body

  htmlBody.style.backgroundImage = 'url(${picture.imgUrl})
}

transition: 1s ease-in-out;
this can help elements that have pseudo classes to change colors and stuff without it being so jarring

class="on-hover" ----- premade by codeworks hides things inside an element, shows them when hovering on the parent