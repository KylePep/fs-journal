<!-- ANCHOR Post_it -->

<!-- TODO -->
* !!!-Initialize repository at workspace level-!!!
* .env --- Our server stuff, should be in slack notes
* Spin up server
* * will require two Auth tokens, one regular token and one incognito token(incognito- sign in- copy sting contents of bearer)
* Postman tests will be provided - Thats cool. They may be difficult to utilize off the bat.
* reate the functions in the order of the postman tests
* bottom of postman console.log request and response body
* create album schema
* Register schema in DbContext - Albums = mongoose.model etc
* Create Controller
* Create Service

<!-- SECTION Keywords -->

* archived: boolean -- "how deleting tends to work. disables viewable data"
* background-image: url() -- background-size: cover; -- background-attachment: fixed; Something like this will make a floating background
* :class="computed property"
* a element you can slot different info into <slot name="header"></slot> <slot name="body"></slot>
  <ModalComponent>
  <template #header>Create Album</template>
  <template #body> <CreateAlbumForm/></template>
  </ModalComponent>
* const router = useRouter
-- router.push({ name: 'Album' , params:{albumId: album.id}})
* v-if="router.name == name: "Album""
* Virtural -- 
<!-- FIXME incomplete -->
AlbumSchema.virual('picture'){
    localField: 'creatorId',
    ref: 'Picture'
    foreignField: '_id',
    justOne: true,
}

* beforeEnter: authSettled -- check and see if you are logged in validate/authenticate
* <picture></picture> - this has some data handling properties that could render something else if a link is broken

<!-- SECTION Example functions -->
bcw create -- express-vue 

**Model/Schema**
  export const AlbumSchema = new Schema({
    title: {tyep: String, required: true, maxLength: 75, minLength: 3}
    category: {type: Sting, enum: ['cats', 'dogs','games'] required: true}
    creatorId: {type: Schema.Types.ObjectId, required: true, ref: 'Account'}
  }, 
  { timeStamps --- referenced in value}) 

  AlbumSchema.virtual('creator',{
    localField: 'creatorId',
    foreignField: '_id',
      })

  **Constroller**
  export class AlbumsController extends BaseController{
    constuctor(){
      super('api/albums')
      this.router
      .get('', this.getAlbums)
      .use(Autho0Provider.getAuthorizedUserInfo)
      .post('', this.createAlbum)
    }

  async createAlbum(req,res,next){
    try{
      const albumData = req.body
      albumData.creatorId = req.userInfo.id
      const album = await albumService.createAlbum.(albumData)
      return res.send()
    } catch (error){
      next(error)
    }
  }

  ** get albums

  }

  **Service**
  class AlbumsService{

    async createAlbum(albumData){
      const newAlbum = await dbContext.Albums.create(albumData)
      await newAlbum.populate('creator', 'name picture')
      return newAlbum
    }

  }
  export const albumsService = new AlbumsService()

  