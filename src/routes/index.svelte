<script lang="ts" context="module">
    import Readme from "../Readme.svelte";

    export const prerender = true;

    const url =
        "https://raw.githubusercontent.com/getcuia/getcuia.github.io/main/README.md";
</script>

<Readme {url} />
