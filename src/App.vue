<template>
  <div id="app">
    <div class="todo" >
      <div class="task-input">
       <input type="text" placeholder="New a Task" >
       <button @click="New_Task('New')">Submit</button>
      </div>
      <div class="taskbox">
        <li class="task">
          <label for="1">
            <input type="checkbox" id ="1">
            <p >Gomo not Support : Change Promotion</p>
            <button @click="Edit_task()">Edit</button>
            <button @click="Delete_task()">Delete</button>
          </label>
        </li>
        <li class="task">
          <label for="1">
            <input type="checkbox" id ="1">
            <p>Gomo not Support : Reconnect - Customer </p>
          </label>
        </li>
        <li class="task">
          <label for="1">
            <input type="checkbox" id ="1">
            <p>Gomo not Support : RequestSuspend - Customer </p>
          </label>
        </li>
        <li class="task">
          <label for="1">
            <input type="checkbox" id ="1">
            <p>Gomo not Support : RequestSuspend - Fraud</p>
          </label>
        </li>
        <li class="task">
          <label for="1">
            <input type="checkbox" id ="1">
            <p>Gomo not Support : Reconnect - Fraud</p>
          </label>
        </li>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {

  },
  methods:{
    New_Task(Add){
      if(Add === 'New')
      console.log(Add)
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
ิbody{
  /* display: none; */
  background: #3c87ff ;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* color: #2c3e50; */
}
.taskbox .task{
  list-style: none;
}
.task label{
  display: flex;
}

</style>
