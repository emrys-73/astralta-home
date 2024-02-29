<script>
    import Button from "$lib/components/ui/button/button.svelte";

    const actionButtons = [
            {
                title: "Full Product Delivery",
                url: "/services/fpd",
                active: true,
            },
            {
                title: "Web Development",
                url: "/services/webdev",
                active: true,
            },
            {
                title: "UI/UX Design",
                url: "/services/design",
                active: true,
            },
            {
                title: "AI",
                url: "/services/ai",
                active: true,
            },

        ]

</script>

<div class="w-full h-full flex gap-4 flex-col justify-center items-center min-h-[90vh] px-4">
    <h1 class="text-5xl sm:text-6xl font-bold">
        Custom Service
    </h1>
    <p class="opacity-60">
        Feel free to tell us all about what you have in mind.
    </p>

    <Button href="mailto:montoya@astralta.com">
        Send us an EMail
    </Button>


</div>

<div class="w-full h-full flex flex-col gap-4 justify-start items-center pb-40">
    <span class="opacity-40">
        Or check out our services
    </span>

    <div class="w-full h-full flex flex-row gap-2 justify-center items-center">
        {#each actionButtons as s}
            {#if s.active}
                <Button href={s.url} class="">
                    {s.title}
                </Button>
            {/if}
        {/each}
    </div>
</div>