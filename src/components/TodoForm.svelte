<script>
  import { todos } from "./store";
  let todo = "";
  const createTodo = (e) => {
    e.preventDefault();
    console.log(todo);
    todos.update((todos) => {
      return [todo, ...todos];
    });
    todo = "";
  };
</script>

<form>
  <label
    >Todo Item
    <input type="text" bind:value={todo} />
    <button on:click={createTodo}>Add Todo</button>
  </label>
</form>
