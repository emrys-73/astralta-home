<script>
// @ts-nocheck

    import InfiniteMovingCards from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingCards.svelte";
    import ContainerScrollAnimation from "$lib/components/ui/ContainerScrollAnimation/ContainerScrollAnimation.svelte";
    import { useTransform, useViewportScroll } from "svelte-motion";
    import GoogleGeminiEffect from "$lib/components/ui/GoogleGeminiEffect/GoogleGeminiEffect.svelte";
    import Spotlight from "$lib/components/ui/Spotlight/Spotlight.svelte";
    import Button from "$lib/components/ui/button/button.svelte";
    import TextGenerateEffect from "$lib/components/ui/TextGenerateEffect/TextGenerateEffect.svelte";
    import { fade, slide, scale } from 'svelte/transition';
	import { onMount } from "svelte";
    import { calendly } from "../../../stores.js"

    let ref;
    const { scrollYProgress } = useViewportScroll();
    const pathLengthFirst = useTransform(scrollYProgress, [0, 0.8], [0.2, 1.2]);
    const pathLengthSecond = useTransform(scrollYProgress, [0, 0.8], [0.15, 1.2]);
    const pathLengthThird = useTransform(scrollYProgress, [0, 0.8], [0.1, 1.2]);
    const pathLengthFourth = useTransform(scrollYProgress, [0, 0.8], [0.05, 1.2]);
    const pathLengthFifth = useTransform(scrollYProgress, [0, 0.8], [0, 1.2]);


    const actionButtons = [
		{
			title: "Full Product Delivery",
			url: "/services/fpd",
			active: false,
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


<div
    class="relative h-[300vh] w-full overflow-clip  pt-60"
    bind:this={ref}
    >
    <GoogleGeminiEffect
        cta="AI X Astralta"
        pathLengths={[
            pathLengthFirst,
            pathLengthSecond,
            pathLengthThird,
            pathLengthFourth,
            pathLengthFifth
        ]}
    />
</div>

<div class="w-full h-full min-h-40 justify-center items-start flex">
    <Button href={calendly} class="rounded-2xl transition-all duration-300 ease-in-out px-8 py-1 hover:px-36 mt-8 bg-green-900 text-white hover:text-black">
        Let's start with a call
    </Button>
</div>

<div class="w-full h-full flex flex-col gap-4 justify-start items-center pb-40">
    <span class="opacity-40">
        Or check out our other services
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