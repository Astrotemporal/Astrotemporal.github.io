<!--<script src="../../../node_modules/flowbite/dist/flowbite.js"></script>-->
<script lang="ts">
    import ProjectPlacard from "./projectPlacard.svelte";

    let clientInformation = {
        x: 0,
        y: 0
    };

    function grabPointer(event: { clientX: number; clientY: number; }) {
        clientInformation.x = event.clientX;
        clientInformation.y = event.clientY;
    }

    const projects = [
        {  // Personal Portfolio!
            title: 'Personal Portfolio',
            body: 'This currently WIP website is a portfolio of my work. The initial version was written in HTML and CSS, and utilized some Bootstrap for the layout. It has now been extended to utilize Svelte. Find the repository of the initial version <a href="https://github.com/uci-inf-133/a1-personal-portfolio-Astrotemporal">here</a>. (sike, it\'s private)'
        },

    ]
</script>

<!---
Some tutorials to revisit:
- https://learn.svelte.dev/tutorial/event-modifiers
- 
-->

<body on:pointermove={(grabPointer)}>
<div id="debugInfo">
    <h1>Debug Information</h1>
    <p>Pointer: {clientInformation.x} x {clientInformation.y}</p>
</div>
<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
It's lit!!!

<div id="projects" class="items-center content-center">
    {#each projects as project (project.title)} 
    <ProjectPlacard {...project} />
    {/each}
</div>
</body>