<script lang="ts" context="module">
    import Projects from "../Projects.svelte";
    import "highlight.js/styles/github.css";
</script>

<Projects />

<slot />

<style>
    @import url("https://gitcdn.link/cdn/dohliam/dropin-minimal-css/gh-pages/min/github-markdown.min.css");

    :global(.hero) {
        margin: 4em 0;
    }

    @media (max-width: 480px) {
        :global(.hero) {
            width: 50%;
        }
    }
</style>
