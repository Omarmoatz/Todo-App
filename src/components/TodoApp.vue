<template>
  <div class="container">
      <h1 class="text-center mt-5">ToDo App</h1>
      <div class="d-flex mt-5">
        <input class="form-control w-100" type="text" placeholder="enter your task" v-model="taskInput">
        <button class="btn btn-warning" @click="submitTask()" type="button">Add</button>
      </div>
  </div>
  <div class="container">
    <table class="table table-striped table-hover mt-5 table-bordered ">
      <thead>
        <tr>
          <th scope="col">Task</th>
          <th scope="col">Status</th>
          <th scope="col">Edit</th>
          <th scope="col">Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(task,index) in tasks" :key='index'>
          <th scope="row">{{task.name}}</th>
          <td>{{task.status}}</td>
          <td>
            <div @click="editTask(index)">
              <span class="fa fa-pen" ></span>
            </div>
          </td>
          <td>
            <div @click="deleteTask(index)">
              <span class="fa fa-trash" ></span>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default{
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      taskInput:'',
      editedTask: null,
      tasks:[
      {
        name:'study english ',
        status:'in progress'
      },
      {
        name:'study vuejs',
        status:'completed'
      }
    ]
    }
  },

  methods:{
    submitTask(){
      if (this.taskInput == 0) return ;
      if (this.editedTask == null){
          this.tasks.push({
          name: this.taskInput,
          status:'todo'
          })
        }
      else{
        this.tasks[this.editedTask].name = this.taskInput
        this.editedTask = null;
      }

      this.taskInput = ''
    },

    deleteTask(index){
      this.tasks.splice(index,1)
    },

    editTask(index){
      this.taskInput = this.tasks[index].name
      this.editedTask= index;
    }
  }

}
</script>

