<template>
  <main>
    <h1>Coding tasks</h1>
    <p>Create a list of coding tasks :</p>

    <div class="create-new">
      <input type="text" v-model="newTask" placeholder="Add a new task" @keypress.enter="addTask" />
      <button @click="addTask">ADD</button>
    </div>

    <div class="tasks">
      <Task v-for="(task, i) in $store.state.tasks"
      :key="i"
      :task="task" />
    </div>

    <div class="footer">
    </div>
  </main>
  
</template>

<script>
export default {
  data (){
    return {
      newTask: ''
    }
  },
  methods: {
    addTask (){
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask);
        this.newTask = '';
      }
    }
  }
}
</script>

