<script lang="ts">
    import Readme from "./Readme.svelte";

    export let name = "getcuia.github.io";
    export let title = "cuia 🌿";
    export let description = "We help make console user interfaces awesome 🌿";

    const url = `https://gitcdn.link/cdn/getcuia/${name}/main/README.md`;
</script>

<svelte:head>
    <title>{title}</title>
    <meta name="description" content={description} />
</svelte:head>

<Readme {url} />
