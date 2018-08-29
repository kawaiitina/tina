<template>
  <v-card>
    <v-form >
        <v-text-field 
            v-model="input" 
            type="text" 
            label="What to do?"
            @keypress.enter="addTodo($event)"
        />

    </v-form>
    <v-btn @click="addTodo">submit</v-btn>
    <v-list>
        <v-list-tile 
        v-for="(todo, i) in todos"
        :key="todo.date"
        @click="deleteTodo(i)"
        >
        <v-list-tile-content>
            <v-list-tile-title v-text="(i + 1) + '. ' + todo.text"/>
        </v-list-tile-content>
        </v-list-tile>
    </v-list>
  </v-card>
</template>

<script>
export default {
  name: 'Todo',
  data(){
      return{
          input: '',
          todos: [
              {
                  text: "play Closers",
                  date: Date.now()
              },
              {
                  text: "delete Closers",
                  date: Date.now() + 1 
              }
            ]
      }
  },
  methods:{
      addTodo(e){
          e.preventDefault();
          this.todos.push({
              text: this.input,
              date: Date.now()
          });
          this.input = '';
      },
      deleteTodo(i){
          this.todos.splice(i,1);
      }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
</style>
