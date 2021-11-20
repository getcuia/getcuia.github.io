<script lang="ts" context="module">
    import Project from "../../Project.svelte";
    export const prerender = true;

    import { page } from "$app/stores";
</script>

<Project name={$page.params.name} />
