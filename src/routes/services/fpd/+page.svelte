<script>
//@ts-nocheck

    import Sparkles from "$lib/components/ui/Sparkles/Sparkles.svelte";
	import CardBody from "$lib/components/ui/ThreeDCardEffect/CardBody.svelte";
	import CardContainer from "$lib/components/ui/ThreeDCardEffect/CardContainer.svelte";
	import CardItem from "$lib/components/ui/ThreeDCardEffect/CardItem.svelte";
	import Button from "$lib/components/ui/button/button.svelte";
	import Spotlight from "$lib/components/ui/Spotlight/Spotlight.svelte";
	import { fade, slide, scale } from 'svelte/transition';
	import { onMount } from "svelte";
    import { twMerge } from "tailwind-merge";
    import TracingBeam from "$lib/components/ui/TracingBeam/TracingBeam.svelte";

	let isMouseEntered = false;

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

    const steps = [
        {
            title: "Product Scope",
            step: "Step One",
            description: `<p class="text-[#838383] font-semibold">
                        We start by <b class="text-white font-semibold">defining</b> exactly what you are looking for in your product. We outline user stories, <b class="text-white font-semibold">key features</b>, main KPIs for the project, as well as the branding and design vision for it.
                    </p>`,
            delieverables: [ "Key Features", "User Stories", "Main Product KPIs" ]
        },
        {
            title: "Key Screens",
            step: "Step two",
            description: `<p class="text-[#838383] font-semibold">
                    We start by creating the <b class="font-semibold text-white">most important screens</b> for your product. This allows you to see exactly how your product will look and then <b class="font-semibold text-white">approve the design</b>.
                </p>`,
            delieverables: ["Key Screens", "Brand identity layout"]
        },
        {
            title: "All Screens",
            step: "Step three",
            description: `<p class="text-[#838383] font-semibold">
                    Once you are happy and approve the Key Screens we <b class="text-white font-semibold">extend the design</b> and deliver the full product UX/UI.
                </p>`,
            delieverables: ["Full Product Mockup"]
        },
        {
            title: "Development",
            step: "Step four",
            description: `<p class="text-[#838383] font-semibold">
                        After your app is fully designed and approved, we start the <b class="text-white font-semibold">implementation phase</b>. During this phase <b class="text-white font-semibold">we progressively deliver the modules of the app</b>, so you can test them during the process.
                    </p>`,
            delieverables: ["Testable Prototype"]
        },
        {
            title: "Test & Launch",
            step: "Step five",
            description: `<p class="text-[#838383] font-semibold">
                        When the app is fully developed we enter a <b class="text-white font-semibold">testing phase</b> during which we’re in constant contact to fix major bugs and make sure your MVP is <b class="text-white font-semibold">ready to go to market</b>.
                    </p>`,
            delieverables: ["Final MVP"]
        },
    ]
   
</script>

<!-- <Spotlight className="-top-[700px] left-0 md:left-60 md:-top-80" fill="white" /> -->
<div class="w-full overflow-auto h-full bg-gradient-to-b from-black to-transparent flex items-center flex-col justify-center gap-40 pt-40 md:pt-0">
    <div class="w-full h-[100vh] flex lg:flex-row flex-col-reverse bg-transparent lg:gap-10 xl:gap-32 gap-20 items-center justify-center pt-80 md:pt-[600px] lg:pt-20">
		<CardContainer bind:isMouseEntered className="inter-var px-8">
			<CardBody
				className="bg-gray-50 relative group/card  dark:hover:shadow-2xl dark:hover:shadow-orange-500/[0.5] dark:bg-black dark:border-white/[0.2] border-black/[0.1] w-80 sm:w-[30rem] h-auto rounded-2xl p-6 border  "
			>
				<CardItem
					{isMouseEntered}
					translateZ="50"
					className="text-2xl font-bold text-neutral-600 dark:text-white pb-6"
				>
					From idea to MVP
				</CardItem>
				<CardItem {isMouseEntered} translateZ="100" rotateX={20} rotateZ={-10} className="w-full mt-4">
					<img
						src="/fpd.png"
						height="1200"
						width="1000"
						class="h-full w-full rounded-xl object-cover group-hover/card:shadow-xl"
						alt="thumbnail"
					/>
				</CardItem>
				<div class="mt-20 flex items-center justify-between">
					<CardItem
						{isMouseEntered}
						translateZ={20}
						translateX={-40}
						className="px-4 py-2 rounded-xl text-xs font-normal dark:text-white"
					>
						<a href="/services/fpd">
							Learn More →
						</a>
					</CardItem>
					<CardItem
						{isMouseEntered}
						translateZ={20}
						translateX={40}
						className="px-4 py-2 rounded-xl bg-black dark:bg-white dark:text-black text-white text-xs font-bold"
					>
						<a href="/">
							Book a call
						</a>
					</CardItem>
				</div>
			</CardBody>
		</CardContainer>

		<div class="flex flex-col gap-2 px-8">
			
			<h1 
            class="scroll-m-20  pb-2 text-7xl lg:text-7xl max-w-[500px] font-semibold tracking-tight transition-colors first:mt-0"
			>
				Full Product Delivery
			</h1>
			<div class="bg-white bg-opacity-10 rounded-full w-max px-4 py-1 ">
				<span>
					Done-For-You
				</span>
			</div>

			<span>
				
			</span>

			<ul class="w-full h-full flex flex-col gap-2 py-6">
				<li class="w-full flex flex-row gap-2 justify-start items-center">
					<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
						<path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12c0 1.268-.63 2.39-1.593 3.068a3.745 3.745 0 0 1-1.043 3.296 3.745 3.745 0 0 1-3.296 1.043A3.745 3.745 0 0 1 12 21c-1.268 0-2.39-.63-3.068-1.593a3.746 3.746 0 0 1-3.296-1.043 3.745 3.745 0 0 1-1.043-3.296A3.745 3.745 0 0 1 3 12c0-1.268.63-2.39 1.593-3.068a3.745 3.745 0 0 1 1.043-3.296 3.746 3.746 0 0 1 3.296-1.043A3.746 3.746 0 0 1 12 3c1.268 0 2.39.63 3.068 1.593a3.746 3.746 0 0 1 3.296 1.043 3.746 3.746 0 0 1 1.043 3.296A3.745 3.745 0 0 1 21 12Z" />
					  </svg>

					  <span>
						Quick Time-To-Market
					  </span>
				</li>
				<li class="w-full flex flex-row gap-2 justify-start items-center">
					<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
						<path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12c0 1.268-.63 2.39-1.593 3.068a3.745 3.745 0 0 1-1.043 3.296 3.745 3.745 0 0 1-3.296 1.043A3.745 3.745 0 0 1 12 21c-1.268 0-2.39-.63-3.068-1.593a3.746 3.746 0 0 1-3.296-1.043 3.745 3.745 0 0 1-1.043-3.296A3.745 3.745 0 0 1 3 12c0-1.268.63-2.39 1.593-3.068a3.745 3.745 0 0 1 1.043-3.296 3.746 3.746 0 0 1 3.296-1.043A3.746 3.746 0 0 1 12 3c1.268 0 2.39.63 3.068 1.593a3.746 3.746 0 0 1 3.296 1.043 3.746 3.746 0 0 1 1.043 3.296A3.745 3.745 0 0 1 21 12Z" />
					  </svg>

					  <span>
						Sign Up Users to your platform
					  </span>
				</li>
				<li class="w-full flex flex-row gap-2 justify-start items-center">
					<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
						<path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12c0 1.268-.63 2.39-1.593 3.068a3.745 3.745 0 0 1-1.043 3.296 3.745 3.745 0 0 1-3.296 1.043A3.745 3.745 0 0 1 12 21c-1.268 0-2.39-.63-3.068-1.593a3.746 3.746 0 0 1-3.296-1.043 3.745 3.745 0 0 1-1.043-3.296A3.745 3.745 0 0 1 3 12c0-1.268.63-2.39 1.593-3.068a3.745 3.745 0 0 1 1.043-3.296 3.746 3.746 0 0 1 3.296-1.043A3.746 3.746 0 0 1 12 3c1.268 0 2.39.63 3.068 1.593a3.746 3.746 0 0 1 3.296 1.043 3.746 3.746 0 0 1 1.043 3.296A3.745 3.745 0 0 1 21 12Z" />
					  </svg>

					  <span>
						Validate ideas with less risk
					  </span>
				</li>
			</ul>

			<div>
				<Button class="rounded-2xl transition-all duration-300 ease-in-out px-8 py-1 hover:px-36 mt-8 bg-orange-600 text-white hover:text-black">
					Start now
				</Button>
			</div>
		</div>
	</div>

    <div id="howitsdone" class="w-full h-full min-h-[20vh] flex flex-col justify-center mt-72 md:mt-96 lg:mt-0 items-center">
        <h2
            class="scroll-m-20 text-5xl sm:text-6xl md:text-7xl font-semibold tracking-tight transition-colors first:mt-0"
            >
            How it works
        </h2>
    </div>

    <div class="w-full h-full min-h-[140vh] flex flex-col justify-start items-center gap-20 px-6">
        {#each steps as s}
            <div class="w-full px-8 py-12 md:w-1/2 h-full justify-center items-center p-4 bg-white bg-opacity-5 rounded-2xl">
                <span class="uppercase font-light text-sm opacity-40">
                    {s.step}
                </span>
                <h3 class="text-3xl font-semibold tracking-wider">
                    {s.title}
                </h3>
                
                <div class="py-4">
                    {@html s.description}
                </div>
                

                <ul class="flex flex-col gap-2 py-6">
                    {#each s.delieverables as d}
                        <li class="flex justify-start items-center flex-row gap-2">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" class="w-6 h-6 stroke-green-500">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
                              </svg>

                            <span>
                                {d}
                            </span>
                        </li>
                    {/each}
                </ul>

            </div>
        {/each}
            <div class="w-full h-full min-h-40 justify-center items-start flex">
                <Button href="https://calendly.com/adrian_cal/meet" class="rounded-2xl transition-all duration-300 ease-in-out px-8 py-1 hover:px-36 mt-8 bg-orange-600 text-white hover:text-black">
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

    </div>


</div>
