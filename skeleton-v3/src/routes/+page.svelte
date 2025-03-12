<script>
    import NavCard from "$lib/components/NavCard.svelte";
    import { routes } from "$lib/utils/routes.js";
</script>

<section
    id="home"
    class="min-h-screen flex flex-col items-center justify-center px-6"
>
    <!-- <HomeView /> -->
    <div
        class="container mx-auto flex justify-center px-4 sm:px-6 lg:px-10 pt-10 pb-5"
    >
        <div class="space-y-4 p-4 flex flex-col items-center text-center">
            <h1 class="md:text-6xl text-5xl font-bold">
                Welcome to a simple template built on the following stack
            </h1>
            <div class="p-4 space-y-4 mt-4">
                <div class="grid grid-cols-4 gap-4">
                    {#each routes as card (card.href)}
                        <NavCard
                            title={card.title}
                            content={card.content}
                            href={card.href}
                            icon={card.icon}
                        />
                    {/each}
                </div>
            </div>
            <div class="space-y-2">
                <p>Try editing the following:</p>
                <p><code class="code">/fastapi/app/ for backend</code></p>
                <p><code class="code">/ui/ for frontend</code></p>
            </div>
            <div class="space-y-2">
                <p>Try exampleitems:</p>
                <a
                    class="btn preset-tonal-secondary"
                    href="/exampleitems"
                    rel="noreferrer"
                >
                    Launch Example
                </a>
            </div>
        </div>
    </div>
</section>
