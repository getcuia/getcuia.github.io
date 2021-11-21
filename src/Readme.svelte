<script lang="ts" context="module">
    import { blur } from "svelte/transition";

    import { marked } from "marked";
    import hljs from "highlight.js/lib/core";

    import bash from "highlight.js/lib/languages/bash";
    import python from "highlight.js/lib/languages/python";
    import shell from "highlight.js/lib/languages/shell";
    hljs.registerLanguage("bash", bash);
    hljs.registerLanguage("python", python);
    hljs.registerLanguage("console", shell);

    marked.setOptions({
        highlight: (code: string, lang: string) => {
            const highlighted = lang
                ? hljs.highlight(code, { language: lang }).value
                : hljs.highlightAuto(code).value;
            return highlighted;
        },
        langPrefix: "hljs language-",
    });

    const fetchReadme = async (url: string): Promise<string> => {
        const response = await fetch(url);
        const text = await response.text();
        return marked(text);
    };
</script>

<script lang="ts">
    export let url: string;
    const readme = fetchReadme(url);
</script>

<main transition:blur>
    {#await readme then html}
        {@html html}
    {:catch error}
        <p>{error}</p>
    {/await}
</main>
