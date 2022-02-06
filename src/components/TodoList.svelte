<script>
    import { todos } from './store'
</script>

<ul>
    {#each $todos as todo}
    <li>{todo}</li>
    {/each}
</ul>