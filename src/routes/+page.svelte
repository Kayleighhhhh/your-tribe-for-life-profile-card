<script>
    import kay from '$lib/assets/kay.jpg';

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

<main>
    <article class="card">
        <header class="tab-bar">
            <p class="tab">+page.svelte</p>
            <!-- <p class="status">Open to internships</p> -->
        </header>

        <section class="body">
            <article class="identity">
                <picture>
                    <img class="avatar" src={kay} alt="kayleigh takening" />
                </picture>
                <section>
                    <h1 class="name">Kayleigh van der Ham</h1>
                    <p class="role">Frontend design & Development Student</p>
                </section>
            </article>

            <p class="bio">
                currently learning Sveltekit, one small project at a time. I
                like to read about all new frontend techniques.
            </p>

            <ul class="stack">
                {#each stack as tech}
                    <li>{tech}</li>
                {/each}
            </ul>

            <footer>
                <p class="comment">// find me elsewhere</p>
                <nav class="links">
                    {#each links as link}
                        <a href={link.href}>{link.label}</a>
                    {/each}
                </nav>
            </footer>
        </section>
    </article>
</main>
