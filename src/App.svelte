<script lang="ts">
  import TasksForm from './components/tasks-form.svelte';
  function addTask(newTask: string){
    console.log(newTask)
  }
</script>

<main>
  <h1>To-Do List</h1>

  <div class="card">
    <TasksForm {addTask} />
  </div>
</main>

<style>
</style>
