<script lang="ts" context="module">
    import { marked } from "marked";

    const readme_url =
        "https://raw.githubusercontent.com/getcuia/getcuia.github.io/main/README.md";

    const fetchReadme = (async (): Promise<string> => {
        const response = await fetch(readme_url);
        const text = await response.text();
        return marked(text);
    })();
</script>

{#await fetchReadme}
    <h1>cuia</h1>
    <p>...</p>
{:then html}
    <p>{@html html}</p>
{:catch error}
    <p>{error}</p>
{/await}

<style>
    @import url("https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800&display=swap");
    :root {
        font-family: "JetBrains Mono", monospace;
    }
</style>
