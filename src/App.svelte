<script lang="ts">
  import TasksForm from './components/tasks-form.svelte';
  import TasksList from './components/tasks-list.svelte';
  import type {Task} from "./types"

  let tasks = $state<Task[]>([])

  function addTask(newTask: string){
    tasks.push({
      id: crypto.randomUUID(),
      title: newTask,
      done: false,
    })
  }

  function toggleDone(task: Task){
    task.done = !task.done;
  }
</script>

<main>
  <h1>To-Do List</h1>

  <div class="card">
    <TasksForm {addTask} />
    <TasksList {tasks} {toggleDone} />
  </div>
</main>

<style>
</style>
