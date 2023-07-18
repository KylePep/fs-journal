# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > main.js

02. What is the difference between a vue `component` and `page`?

  > A page is a part of the path in the routes in the index, creating the "page" or visible field on the selected portion of the website, a component is a portion of the web page exported out to another file that has all the parts necessary to create a function html and javascript.

  Whole- -part

03. What is ***Component-Based Architecture***?

  > | ANSWER HERE |

04. What are the three tags that make up a Vue component?

  > <template></template>,<script></script>,<style></style>

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > onMountded, onUpdated, onUnmounted, what to do when the page does (x) ie the page loads

06. Which component in Vue does the vue-router use to mount pages onto?

  > | ANSWER HERE |

07. What is the difference between the `AppState` and the state object within a component?

  > The AppState is were all of the data should be stored for the application, the state is where the javascript runs within the scope

08. What is the responsibility of `Services` in our Vue projects?

  > The same, it is still where information goes to be changed and then sent up to the AppState.

09. What are ***props*** and how are they used? Provide an example

  > Props are a child function that pulls information down from a parent to a child like when v-for-ing over a collection

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > reactive, ------ may need to expand
