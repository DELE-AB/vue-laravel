<template>
  <div class="container">
    <Header title="Task Tracker" @toggle-add-task="toggleAddTask" :showAddTask="showAddTask" />
    <div v-show="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks @toggle-Reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from "./components/Tasks" 
import AddTask from "./components/AddTask"
export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data(){
    return {
        tasks:[],
        showAddTask:true,
    }
  },
  methods:{
    toggleAddTask(){
      this.showAddTask= !this.showAddTask
    },
    addTask(task){
      this.tasks =[...this.tasks,task];
    },
    deleteTask(id){
      if(confirm('Are you sure')){
        this.tasks = this.tasks.filter((task)=> task.id !==id );
      }
      
    },
    toggleReminder(id){
      this.tasks = this.tasks.map((task) => 
      task.id === id ? {...task, reminder: !task.
      reminder} :task
      )
      console.log('the click is working');
    },
  },
  created(){
      this.tasks = [
          {
              id:1,
              text: "Doctors Appointment",
              day: "March 1st at 2:30pm",
              reminder:true,
          },
            {
              id:2,
              text: "Meetings at school",
              day: "March 3rd at 1:30pm",
              reminder:true,
          },
            {
              id:3,
              text: "Food Shopping",
              day: "March 3rd at 1:30pm",
              reminder:false,
          },
        
      ]
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: sans-serif;
}

.container{
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn{
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
</style>
