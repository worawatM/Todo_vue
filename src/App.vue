<template>
  <div id="app">
    <div class="todo">
      <div class="task-input">
        <input v-model="addtask" type="text" placeholder="New a Task" />
        <button @click="New_Task(' ')">Submit</button>
      </div>

      <div class="taskbox">
        <!-- <li class="task">
          <label>
            <input type="checkbox" id="1" />
            <p>Gomo not Support : Change Promotion</p>
            <button @click="Edit_task()">Edit</button>
            <button @click="Delete_task()">Delete</button>
          </label>
        </li> -->
        
        <div v-for="(item, index) in arr" :key="index">
          <li class="task">
            <label>
              <input type="checkbox" id="1" />
              <p>{{ item }}</p>
              <button @click="Edit_task()">Edit</button>
              <button @click="Delete_task()">Delete</button>
            </label>
          </li>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  data() {
    return {
      addtask: "",
      arr: [],
    };
  },
  components: {},
  methods: {
    New_Task() {
      // this.i++
      this.arr.push(this.addtask)
      this.addtask = ""
      console.log(this.arr)
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
ิbody {
  /* display: none; */
  background: #3c87ff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* color: #2c3e50; */
}
.taskbox .task {
  list-style: none;
}
.task label {
  display: flex;
}
</style>
