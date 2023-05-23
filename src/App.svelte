<script>
    import TaskDescription from "./TaskDescription.svelte";

  let tasks = [];
  let newTask = {id:'',name: '',description :'',type : 'basic'};

  function addTask() {
	newTask.id = tasks.length;
    tasks = [...tasks, newTask];
    newTask = {};
  }

  function deleteTask(index) {
    tasks = tasks.filter((_, i) => i !== index);
  }
</script>

<h1>Task Manager</h1>

<input type="text" bind:value={newTask.name} placeholder="Enter a task" />
<input type="text" bind:value={newTask.description} placeholder="Enter a Description" />

<div>
	<span>Select a type:</span>
	<button on:click={() => newTask.type = 'basic'} class:selected={newTask.type === 'basic'}>Basic</button>
	<button on:click={() => newTask.type = 'emergency'} class:selected={newTask.type === 'emergency'}>Emergency</button>
	<button on:click={() => newTask.type = 'todo'} class:selected={newTask.type === 'todo'}>To Do</button>
  </div>
<button on:click={addTask}>Add Task</button>

<TaskDescription tasks={tasks}/>
   