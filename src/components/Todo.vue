<template>
  <v-app>
       <v-main>
        <v-container>
       <v-card
    class="mx-auto middle pa-10"
    max-width="900"
  >
    <v-card-text>
      <h1 class="text-xs-display-1 text-center pa-1">
        TODO APP USING VUE JS
      </h1>
      <div class="text--primary">
        <v-form autocomplete="off" @submit.prevent = "addTodo()">
    <v-text-field v-model = "newTodo" label="Enter Todo"></v-text-field>
  </v-form>
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn color="success darken-1" @click = "addTodo()" v-if = "newTodo.length > 0">
     Enter Todo
    </v-btn>
    </v-card-actions>
  </v-card>
  <!-- SHOWING THE CARD WHEN THERE IS NOTHING -->
  <div v-if = "todos.length == 0" >
    <v-card class="mx-auto my-6" max-width = "900" >
      <v-list>
        <v-list-item-group class="text-center">
          <h1 class="text-sm-display-2 text--secondary"> Todo List Empty</h1>
        </v-list-item-group>
        <v-list-item>
          <v-list-item-content class="pa-3">
            <v-list-item-title class="my-2"> ADD NEW TODOS</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-card>
  </div>
  <!-- SHOWING THE DYNAMIC TODO -->
  <div v-show = "todos.length > 0">
    <v-card class="mx-auto my-6" max-width = "900" >
    <v-list>
      <v-list-item-group class="text-center">
        <h1 class="text-sm-display-2 text--secondary"> Todos List</h1>
      </v-list-item-group>
      <v-list-item v-for = "(todo,i) in todos" :key="i">
        <v-list-item-content class="pa-3">
          <v-list-item-title class="my-2"> {{todo}} <v-btn class="error darken-1 float-right" @click = "todos.splice(i,1)">Delete <v-icon>mdi-delete</v-icon> </v-btn></v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-card>
  </div>
     </v-container>
        </v-main>
      <!-- FOOTER FOR THE TODO APP -->
          <v-footer
            padless = false
            v-bind="localAttrs"
          >
            <v-card
              flat
              tile
              width="100%"
              class="green darken-2 text-center"
            >
            <div class="d-flex align-center">
              <v-card-text>
                <v-btn
                  class="mx-4"
                  icon
                >
                  <v-icon size="34px" color="white">
                    mdi-whatsapp
                  </v-icon>
                </v-btn>
              </v-card-text>
              <!-- SECOND ICON -->
              <v-card-text>
                <v-btn
                  class="mx-4"
                  icon
                >
                <v-icon size="34px" color="white">
                   mdi-twitter
                  </v-icon>
                </v-btn>
              </v-card-text>
                <!-- THIRD ICON -->
                <v-card-text>
                  <v-btn
                    class="mx-4"
                    icon
                  >
                  <v-icon size="34px" color="white">
                      mdi-facebook
                    </v-icon>
                  </v-btn>
                </v-card-text>
                <!-- FOURTH ICON -->
                  <!-- SECOND ICON -->
              <v-card-text>
                <v-btn
                  class="mx-4"
                  icon
                >
                <v-icon size="34px" color="white">
                    mdi-github
                  </v-icon>
                </v-btn>
              </v-card-text>
            </div>  
          <v-divider></v-divider>
      
              <v-card-text class="white--text">
                <strong>A Todo App Built With Vue Js By Lekan Dar</strong> - {{ new Date().getFullYear() }}
              </v-card-text>
            </v-card>
          </v-footer>
  </v-app>
</template>

<script>
export default {
    name: "Todo",
    data: function () {
        return {
            newTodo: "",
            header: "Welcome To Vue Js",
            reveal: false,
            todos : []
        }
    },
     methods:{
       addTodo: function(){
         this.todos.push(this.newTodo)
         this.newTodo = ""
       }
     },
}
</script>

<style>

</style>