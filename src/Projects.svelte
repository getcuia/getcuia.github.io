<script>
    import { page } from "$app/stores";

    const nav = [
        {title: "🏡 home", path: "/"},
        {title: "🖍️ stransi", path: "/tldr/stransi"},
        {title: "🏜️ ochre", path: "/tldr/ochre"},
    ];
</script>

<nav>
    <ul>
        {#each nav as link}
            <li><a class:active={$page.path === link.path} rel="external" href={link.path}>{link.title}</a></li>
        {/each}
    </ul>
</nav>

<style>
    nav {
        margin-bottom: 4em;
    }
    li {
        display: inline-block;
    }
    li:after {
        content: " | ";
    }
    li:last-child:after {
        content: "";
    }

    .active {
        color: gray;
        text-decoration: none;
    }
</style>
