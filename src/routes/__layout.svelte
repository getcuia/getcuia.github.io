<script lang="ts">
    import "highlight.js/styles/github.css";
</script>

<slot />

<style>
    @import url("https://gitcdn.link/cdn/dohliam/dropin-minimal-css/gh-pages/min/github-markdown.min.css");

    :global(.logo) {
        margin: 4em 0;
    }

    @media (max-width: 480px) {
        :global(.logo) {
            width: 50%;
        }
    }
</style>
