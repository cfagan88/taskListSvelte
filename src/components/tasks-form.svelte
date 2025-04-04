<script lang="ts">
let newTask = $state("");
let { addTask } : {addTask: (newTask: string) => void} = $props();

function handleSubmit(e: SubmitEvent) {
  e.preventDefault()
  addTask(newTask)
  newTask="";
}
</script>


<form onsubmit="{handleSubmit}">
  <label>
    <input name="newTask" bind:value={newTask}/>
  </label>
  <div class="button-container">
  <button>Add</button>
    </div>
</form>


<style>
 input {
  height: 30px;
  width: 600px;
 }
 .button-container {
  display: flex;
  justify-content: end;
  margin-top: 8px;
 }
 form {
  margin-bottom: 1rem;
 }
</style>