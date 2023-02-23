<template>
  <div id="app">
    <div class="todo">
      <div class="task-input">
        <input v-model="addtask" type="text" placeholder="New a Task" />
        <button @click="NewTask">{{statebutton}}</button>
      </div>

      <div class="taskbox">
        
        <div class="taskLine" v-for="(item, index) in arr" :key="index">
          <li v-if="!item.isDone" class="task">
            
              <input  type="checkbox"  @input="checkout_task(index,item)"  />
              <span>{{ item.value }}</span> 
              <button @click="Edit_task(index)">Edit</button>
              <button @click="Delete_task(index)">Delete</button>
            
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
      statebutton : 'Submit' ,
      addtask: "",
      editTask: null,
      arr: [

      ],
    };
  },
  components: {
  },
  methods: {
    NewTask() {
      // this.arr.push(this.addtask)
      // this.addtask = ""
      // console.log(this.arr)
      if(this.addtask.length !== 0 && this.statebutton !== 'Update' ){
          this.arr.push(
                {
                  value: this.addtask,
                  isDone : false
                }
            )
          this.addtask = ''
         console.log(1) 
      }
      else if(this.editTask === null){
          return;
      }
      else{
        this.arr[this.editTask].value = this.addtask
        // this.arr[this.editTask].isDone = false
        this.editTask = null
        this.statebutton ='Submit'
        this.addtask = ''
        console.log(2)
      }
      // this.addtask = ''
      console.log(this.arr)

    },
    Delete_task(idx){
        this.arr.splice(idx, 1) 
        // console.log(idx,item)
    },
    checkout_task(index){
       this.arr[index].isDone = true
    },
    Edit_task(idx){
      this.addtask = this.arr[idx].value
      this.editTask = idx
      this.statebutton ='Update'
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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* color: #2c3e50; */
  background: greenyellow;
  
    height: 100vh;
}
.taskbox .task   {
  list-style: none;
}
.taskLine {
  display: flex;

}
</style>
