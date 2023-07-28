# Managing the Fullstack Application

1. Describe the two ways to bind Data in Vue?

  > with the colons :src="data.data" -- Binding the attribute to the data
  v-model  -- 

2. The `SPA` acronym stands for what?

  > Single Page application

3. What are some of the advantages/uses of a `SPA` over a traditional one?

  > + Faster resources loaded on launch dont need to be reloaded
  - More work for the browser, risk of memory leaks

4. What does the `onMounted` method in Vue do?

  > When the component loads it does the actions stored inside

5. What is the `v-model` attribute in Vue for, and when might you use it?

  > v-model is used to interact with a referenced value, used commonly for forms

6. What is the package.json file used for?

  > Contains descriptive and functional metadata about a project, such as a name, and dependencies.

7. Which Vue attributes(directives) could you use to conditionally render elements on a page?

  > V-if -- You can attach this to a computed variable and when that value returns false it wont render the contents

8. What is the purpose of the `key` attribute when using `v-for` on an element?

  > The key attribute is basically the i in a for loop. It makes sure not to interact with the same set of data over again and makes sure it doesnt have to check deeper into the data to verify it has in fact made the change.

9. What is the `<slot>` element and what is it used for?

  > a element you can slot different info into <slot name="header"></slot> <slot name="body"></slot>
  <ModalComponent>
  <template #header>Create Album</template>
  <template #body> <CreateAlbumForm/></template>
  </ModalComponent>
