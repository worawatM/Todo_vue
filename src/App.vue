<template>
  <div id="app">
    <div class="todo">
      <div class="task-input">
        <input v-model="addtask" type="text" placeholder="New a Task" />
        <button @click="New_Task(' ')">Submit</button>
      </div>

      <div class="taskbox">
        
        <div v-for="(item, index) in arr" :key="index">
          <li class="task">
            <label>
              <input type="checkbox" id="1" />
              <p>{{ item.value }}</p>
              <button @click="Edit_task(index)">Edit</button>
              <button @click="Delete_task(index)">Delete</button>
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
      editTask: null,
      arr: [
        {
          value: 'Gomo test : change sim',
        }
      ],
    };
  },
  components: {
  },
  methods: {
    New_Task() {
      // this.arr.push(this.addtask)
      // this.addtask = ""
      // console.log(this.arr)
      if(this.addtask.length !== null && this.editTask === null){
          this.arr.push(
                {
                  value: this.addtask,
                }
            )
          this.addtask = ''
        //  console.log(1) 
      }

      else{
        this.arr[this.editTask].value = this.addtask
        this.editTask = null
        this.addtask = ''
      }
      console.log(this.arr)

    },
    Delete_task(idx){
        this.arr.splice(idx, 1) 
    },

    Edit_task(idx){
      this.addtask = this.arr[idx].value
      this.editTask = idx
    }
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
  width: 100%;
  height: 100vh;
  overflow: hidden;
  background: #4AB1FF;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* color: #2c3e50; */
  background: greenyellow
  
}
.taskbox .task {
  list-style: none;
}
.task label {
  display: flex;
}
</style>
