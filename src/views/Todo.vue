<template>
  <div class="home">
    <v-list
    class="pt-0"
      
      flat
    >
    <v-text-field
    v-model="newTaskTitle"
    @click:append="addEvent"
    @keyup.enter="addEvent"
    class="pa-4"
    outlined
    label="Add Task"
    append-icon="mdi-plus"
    hide-details
    clearable
    >
    </v-text-field>
 

<div 
v-for="task in tasks"
:key="task.id">

  
        <v-list-item 
        @click="doneTask(task.id)"
        :class="{'blue lighten-5' : task.done}"
        >
        
        
          <template v-slot:default>
            <v-list-item-action>
              <v-checkbox
                :input-value="task.done"
                color="primary"
              ></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title
             :class="{'text-decoration-line-through' : task.done }" 
             >
             {{task.title}}
              </v-list-item-title>
            </v-list-item-content>
            <v-list-item-action>
              <v-btn 
              icon
              @click.stop="deleteTask(task.id)">
                <v-icon color="primary lighten-3"> mdi-delete </v-icon>
              </v-btn>
            </v-list-item-action>
          </template>
        </v-list-item>
        <v-divider></v-divider>
        
   

</div>
 </v-list>


    
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data() {
    return {
      newTaskTitle: '',
      tasks: [
        {
          id: 1,
          title: "Wake up",
          done: false
        },
          {
          id: 2,
          title: "Make coffee",
           done: false

        },
          {
          id: 3,
          title: "Drink coffee",
          done: false

        },
      ],
      snackbar: false,
      text: `Hello, I'm a snackbar`,
    }
  },
  methods: {
    addEvent() {
      let newTask ={
        id: Date.now(),
        title: this.newTaskTitle,
        done: false
      }
      this.tasks.push(newTask)
      this.newTaskTitle= ''


    },
    doneTask(id) {
      let task = this.tasks.filter(task => task.id === id)[0]
      task.done = !task.done
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id)
    }
  }
 
}
</script>
