<script lang="ts">
  import type {Task} from "../types"
  let { tasks, toggleDone }: {tasks: Task[]; toggleDone: (task: Task) => void;} = $props()
</script>

<section>
  {#each tasks as task}
  <article>
    <label>
      {task.title}
      <input onchange={() => toggleDone(task)} checked={task.done} type="checkbox" />
    </label>
  </article>
  {/each}
</section>

<style>
  article {
    background-color: rgb(55, 69, 95);
    /* update task items styling */
  }
</style>