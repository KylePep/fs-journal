Notes 6/26

Maybe start researching Api's for capstone

------------Zelda breath of the wild API--------------

hyrule Compendium API

Create Controller
MonstersController.js

getMonsters(){
      try{
        monstersService.getMonsters()
        Pop.success('got monsters')
    } catch (error){
        console.error(error)
        Pop.error(error.message)
    }
}

Create Service
MonstersService.js

<!-- hard way -->
async getMonsters(){
  const response = await fetch( ----monster relavent url----)
  const jsonData = await response.json()
}

<!-- easy way -->
async getMonsters(){
      try{
        await monstersService.getMonsters()
        Pop.success('got monsters')
    } catch (error){
        console.error(error)
        Pop.error(error.message)
    }
}

async getMonsters(){
    const response = await zeldaApi.get('category/monster')
}

Create AxiosService

export const zeldaApi = axios.create({
    baseUrl: 'htttp: zelda compendium api url'
    timeout: 8000
})

