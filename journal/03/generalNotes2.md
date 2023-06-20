<!--  general notes on day 2 -->
bcw create
tip: CTRL+P to navigate
<!-- SECTION gatchamon -->
remove view from html and turn view: '' into an empty string in the router

controller: [CoinsController,GachamonsController],

html
button---  onclick="app.CoinsController.addCoing()"
-----id = "coinCount"
<!-- SECTION appstate -->
App.state within eventEmitter block{
  coins = 0  // new is not required because it is not being created from a class, model

  gachamons = [
    new Gachamon({name: 'Mikey', emoji: '🤖', rarity: 'ultra-rare'}),
    new Gachamon({name: 'LJ', emoji: '🦞', rarity: 'common'}),
    new Gachamon({name: 'Rodney', emoji: '🐍', rarity: 'rare'}),
  ]

  activeGachamon = null
}

create CoinsController.js

<!-- SECTION CoinCONTROLLER -->
--outside of the coin controller--
function _drawCoins(){
  let stringOfCoins = ''
  for(let i = 0; i < AppState.coins; i++){
    stringOfCoins += '🪙'
  }

    setText('coinsCount', stringOfCoins)
}

export class CoinsController{
  constructor(){

  }

  addCoin(){
    coinsService.addCoin()
    _drawCoins()
  }
}
<!-- SECTION CoinSERVICE -->
create CoinsService.js
---singleton---

class CoinsService {
    addCoin(){
      AppState.coins++
    }
}

export const coinsService = new CoinsService()

<!-- SECTION Gachamon model -->
create Gachamon.js

export class Gachamon{
  constructor(data){
    this.name = data.name
    this.rarity = data.rarity
    this.emoji = data.emoji
  }

  <!-- NOTE never ever write out HTML by hand, write it in the index then copy paste-->
  get GachamonsSmallTemplate(){    -----------getters do not need to be invoked with() later in other objects
    return `
    div
      div onclick="app.GachamonsController.showcaseGachamon('this.name')"
      p
    div 
    `
  }

  get GachamonsLargeTemplate(){    -----------getters do not need to be invoked with() later in other objects
    return `
    div
      
      
    div 
    `
  }
}

<!-- SECTION Gachamon Controller -->
function _drawGachamons(){
  const gachamons = AppState.gachamons
  let template = ''
  gachamons.forEach(gachamon => template += gachamon.GachamonsSamllTemplate)
  setHTML(gachamonCatalog,template)

}

function _drawActiveGachamon(){
  const SingleGachamon = AppState.activeGachamon
  setHTML('activeGachamon', singleGachamon.)
}

export class GachamonsController {
  constructor(){
    _drawGachamons()
  }
  showcaseGachamon(gachamonName){
      gachamonsService.showcaseGachamon()
      _drawActiveGachamon()
  }
}

<!-- SECTION Gachamons Service -->

class GachamonsService {

showcaseGachamon(gachamonName){
  const gachamons = AppState.gachamons
  const foundGachamon = gachamons.find(g => g.name == gachamonName)

  AppState.activeGachamon = foundGachamon
}
}

export const gachamonsService = new GachamonsService()


<!-- SECTION listener -->
Coins Controller

listener

inside of constructor() {
  appState.on('coins', _drawCoins)
}

AppState.emit('myGachamons')


let random index = Math.floor(Math.random()*gachamons.length)

<!-- SECTION Saving -->


function _saveMyGachamons(){
  saveState('myGachamons',AppState.myGachamons)
}

after pushing Gachamon into array perform the _saveMyGachamons()

<!-- SECTION Loading -->

AppState

myGachamons = loadState('myGachamons',[Gachamon])