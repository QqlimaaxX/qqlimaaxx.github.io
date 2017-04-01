<template>
  <div id="app">
    <todo-list :todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
    TodoList
  },
  data(){
    return{
      todos:[
        {
        title:'Complete Math Assignment',
        desc:'Submission on Monday shit',
        done:false
        },{
        title:'CSA Assignment also',
        desc:'ON Monday',
        done:false
        },{
        title:'Get Lab Manuals Checked',
        desc:'DO IT FAST IDIOT',
        done:false
        }
      ]
    }
  }
}
</script>

<style>
</style>
