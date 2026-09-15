<script>
    let stack = ["Svelte", "HTML", "CSS", "NodeJs"];

    let links = [
        { label: "GitHub", href: "https://github.com/Kayleighhhhh" },
        {
            label: "LinkedIn",
            href: "https://www.linkedin.com/in/kayleigh-van-der-ham-952576267/",
        },
        {
            label: "Bluesky",
            href: "https://bsky.app/profile/kayleighhhhh.bsky.social",
        },
    ];

</script>

<article class="card">
    <header class="tab-bar">
        <span class="tab">
            <span class="unsaved-dot" title="Always a work in progress"></span>
            +page.svelte
        </span>
        <span class="status">
            <span class="status-dot"></span>
            Open to internships
        </span>
    </header>

    <section class="body">
        <article class="identity">
            <div class="avatar">KvdH</div>
            <section>
                <h1 class="name">Kayleigh van der Ham</h1>
                <p class="role">Frontend design & Development Student</p>
            </section>
        </article>

        <p class="bio">
            currently learning Sveltekit, one small project at a time. I like
            interfaces that feel instant and write up what breaks along the way.
        </p>

        <ul class="stack">
            {#each stack as tech}
                <li>{tech}</li>
            {/each}
        </ul>

        <footer>
            <p class="comment">// find me elsewhere</p>
            <nav class="links">
                {#each links as link, i}
                    <a href={link.href}>{link.label}</a>
                    {#if i < links.length - 1}<span class="sep">·</span>{/if}
                {/each}
            </nav>
        </footer>
    </section>
</article>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&family=JetBrains+Mono:wght@400;500&display=swap");

    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    :root {
        --paper: #fbfaf7;
        --ink: #1c1d21;
        --ink-soft: #55575e;
        --line: #d8d5cc;
        --accent: #3d5a80;
        --accent-soft: #e7ecf2;
        --gold: #e0a458;
    }

    .card {
        font-family: "Space Grotesk", system-ui, sans-serif;
        color: var(--ink);
        background: var(--paper);
        border: 1px solid var(--line);
        border-radius: 10px;
        max-width: 420px;
        width: 100%;
        margin: 0 auto;
        margin-top: 5em;
        box-shadow: 0 1px 2px rgba(28, 29, 33, 0.04);
        transition:
            transform 0.18s ease,
            box-shadow 0.18s ease;
    }

    .card:hover {
        transform: translateY(-2px);
        box-shadow: 0 10px 24px rgba(28, 29, 33, 0.08);
    }

    @media (prefers-reduced-motion: reduce) {
        .card {
            transition: none;
        }
        .card:hover {
            transform: none;
        }
    }

    .tab-bar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0.6rem 1rem;
        border-bottom: 1px solid var(--line);
        font-family: "JetBrains Mono", monospace;
        font-size: 0.78rem;
    }

    .tab {
        display: flex;
        align-items: center;
        gap: 0.45rem;
        color: var(--ink-soft);
    }

    .unsaved-dot {
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background: var(--gold);
        flex-shrink: 0;
    }

    .status {
        display: flex;
        align-items: center;
        gap: 0.4rem;
        color: var(--ink-soft);
    }

    .status-dot {
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background: var(--accent);
    }

    .body {
        padding: 1.25rem 1.25rem 1.4rem;
    }

    .identity {
        display: flex;
        align-items: center;
        gap: 0.9rem;
        margin-bottom: 1rem;
    }

    .avatar {
        width: 48px;
        height: 48px;
        border-radius: 8px;
        background: var(--accent-soft);
        color: var(--accent);
        font-family: "JetBrains Mono", monospace;
        font-weight: 500;
        font-size: 0.9rem;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-shrink: 0;
    }

    .name {
        margin: 0;
        font-size: 1.25rem;
        font-weight: 700;
        line-height: 1.2;
    }

    .role {
        margin: 0.15rem 0 0;
        font-size: 0.88rem;
        color: var(--ink-soft);
    }

    .bio {
        margin: 0 0 1.1rem;
        font-size: 0.92rem;
        line-height: 1.55;
        color: var(--ink);
        max-width: 62ch;
    }

    .stack {
        list-style: none;
        display: flex;
        flex-wrap: wrap;
        gap: 0.4rem;
        padding: 0;
        margin: 0 0 1.25rem;
    }

    .stack li {
        font-family: "JetBrains Mono", monospace;
        font-size: 0.76rem;
        background: var(--accent-soft);
        color: var(--accent);
        padding: 0.25rem 0.55rem;
        border-radius: 4px;
    }

    footer {
        border-top: 1px solid var(--line);
        padding-top: 0.85rem;
    }

    .comment {
        font-family: "JetBrains Mono", monospace;
        font-size: 0.76rem;
        color: var(--ink-soft);
        margin: 0 0 0.5rem;
    }

    .links {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        gap: 0.4rem;
        font-size: 0.88rem;
    }

    .links a {
        color: var(--ink);
        text-decoration: none;
        border-bottom: 1px solid var(--line);
    }

    .links a:hover {
        color: var(--accent);
        border-color: var(--accent);
    }

    .links a:focus-visible {
        outline: 2px solid var(--accent);
        outline-offset: 2px;
        border-radius: 2px;
    }

    .sep {
        color: var(--line);
    }

    @media (max-width: 380px) {
        .body {
            padding: 1rem;
        }
        .identity {
            gap: 0.7rem;
        }
    }
</style>
