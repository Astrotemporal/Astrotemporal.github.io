<script lang="ts">
    import { createEventDispatcher } from "svelte";
    import { Card } from 'flowbite-svelte';

    export let title: String;
    export let body: String;

    const dispatch = createEventDispatcher(); // use for even more interactibility on project placards


</script>

<Card href="/projects/{title.replace(/\s/g, "")}" color="primary" id={title.replace(/\s/g, "")}>
    <h1>{@html title}</h1>
    <p>{@html body}</p>
</Card>
