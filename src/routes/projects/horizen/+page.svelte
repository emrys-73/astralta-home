<script>
// @ts-nocheck
    import IntersectionObserver from "svelte-intersection-observer";
    import InfiniteMovingBoxes from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingBoxes.svelte";
	import InfiniteMovingCards from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingCards.svelte";
	import InfiniteMovingHeader from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingHeader.svelte";
	import { fade, slide, scale, fly, blur } from 'svelte/transition';
	import { onMount } from "svelte";
    import { quintOut, cubicInOut, quintInOut } from 'svelte/easing';
    import { footerColor, endcta } from "../../../stores";

    onMount( async () => {
        footerColor.set("bg-gradient-to-b from-[#FF620B] to-[#000000]")
    })

    let header;

    const testimonials = [
		{
			quote:
				"To be, or not to be, that is the question: Whether 'tis nobler in the mind to suffer The slings and arrows of outrageous fortune, Or to take Arms against a Sea of troubles, And by opposing end them: to die, to sleep.",
			name: 'William Shakespeare',
			title: 'Hamlet',
      content: 'HORIZEN ✱',
		},
		{
			quote: 'All that we see or seem is but a dream within a dream.',
			name: 'Edgar Allan Poe',
			title: 'A Dream Within a Dream',
      content: 'HORIZEN ✱',
		},
		{
			quote:
				'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
			name: 'Jane Austen',
			title: 'Pride and Prejudice',
      content: 'HORIZEN ✱' ,

		},
		{
			quote:
				'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.',
			name: 'Herman Melville',
			title: 'Moby-Dick',
      content: 'HORIZEN ✱',
		}
	];

	let mainmockup;
	let headline;


	let aiheader;
	let aispecs;

	let deliv;
	let brief;
	let solution;

	let final;

	let cta;

</script>

<div class="w-full flex flex-col justify-center items-center">
	<IntersectionObserver element={header} let:intersecting>
		<div bind:this={header} class="min-h-[90vh]">
		 {#if intersecting}
			<div
				transition:fly={{ delay: 10, duration: 1000, y: -400 }} 
				class=""
				>
				<InfiniteMovingCards items={testimonials} direction="right" speed="slow"/>
				<InfiniteMovingCards items={testimonials} direction="left" speed="slow"/>

				<span class="w-full opacity-50 flex text-center justify-center items-center pt-10  md:pt-40">
					(Scroll to explore)
				</span>
			</div>

		  {/if}
		</div>
	  </IntersectionObserver>
</div>

<div class="w-full h-full md:min-h-[110vh] min-h-[70vh] sm:min-h-[90vh] bg-[url('/bgs/org.jpg')] bg-cover flex flex-col justify-center items-center overflow-hidden">
	<IntersectionObserver element={mainmockup} let:intersecting>
		<div bind:this={mainmockup} class="">
			{#if intersecting}

			<div
				transition:fly={{ delay: 2, duration: 2500, y: -800 }} 
				class=""
			>
				<img src="/mockups/hrzn.png" alt="hrzn" class=" scale-150 ml-40 md:scale-100 md:ml-0">
			</div>

			{/if}
		</div>

	</IntersectionObserver>
</div>

<div class=" w-full h-full md:min-h-[100vh] min-h-[120vh] flex flex-col md:flex-row px-6 md:px-10 lg:px-20 bg-black overflow-hidden  justify-center items-start md:py-[10vh] lg:pt-[20vh]">
	<div class="w-1/4 h-full pt-2 shrink-0 py-6 md:py-0">
		✱ HEADLINE
	</div>

	<div class="w-auto h-full flex ">
		<IntersectionObserver element={headline} let:intersecting>
		<div bind:this={headline}>
			{#if intersecting}
			<div>
			<div transition:fly={{ delay: 50, duration: 2500, x: 800, y: 0, opacity: 0.01, easing: quintOut }}>
				<p class="text-3xl md:text-4xl lg:text-5xl font-thin">
					A fully custom web application for a digital marketing agency managing clients with multiple properties each.

					<br>
					<br>
					Focused on merging AI with Hotel-Booking systems HoRizen achieved record growth through enhanced customer experience using their own platform.
				</p>
		
			</div>
			</div>
			{/if}
		</div>
		</IntersectionObserver>
	</div>
</div>


<div class="w-full h-full bg-[#FF620B] relative flex flex-col xl:flex-row min-h-[80vh] sm:min-h-[90vh] lg:min-h-[90vh]">

	<div class="w-full h-auto flex flex-col justify-start items-start px-8 py-10">
		<IntersectionObserver element={aiheader} let:intersecting>
			<div bind:this={aiheader} class="">
			 {#if intersecting}
				<div
					transition:fly={{ delay: 10, duration: 1000, y: -400 }} 
					class=""
					>
					<h2 class=" text-4xl sm:text-5xl lg:text-6xl xl:text-8xl font-bold text-white uppercase flex justify-start items-start text-start ">
						✱ HORIZEN
					</h2>
					</div>
				{/if}
			</div>
		</IntersectionObserver>
	</div>

	<div class="w-full h-auto flex flex-col justify-start xl:py-20 xl:items-center items-start lg:px-[10vw] lg:pl-[15vw] px-8">
		<IntersectionObserver element={aispecs} let:intersecting>
			<div bind:this={aispecs} class="">
			 {#if intersecting}
				<div
					transition:fly={{ delay: 10, duration: 1000, x: 400 }} 
					class="overflow-hidden"
					>
					<ul class="w-full h-full gap-6 flex flex-col text-xl lg:text-2xl font-light justify-center items-start">
					<li>
							✱ Optimal pricing analytics & prediction
						</li>
						<li>
							✱ Sentiment analysis for clients and customers
						</li>
						<li>
							✱ Chat interface for booking and management
						</li>
						<li>
							✱ Customer trend analytics
						</li>
					</ul>
					</div>
				{/if}
			</div>
		</IntersectionObserver>
	</div>
	<img src="/mockups/hrznai.png" alt="" class="absolute bottom-0">
</div>


<div class=" w-full h-full min-h-[120vh] flex flex-col md:flex-row px-6 md:px-10 lg:px-20 bg-black overflow-hidden  pt-[20vh]">
	<div class="md:w-1/4 w-full h-full pt-2 shrink-0 ">
		✱ THE STORY
	</div>

	<div class="w-auto h-full flex flex-col gap-10">
		<IntersectionObserver element={deliv} let:intersecting>
		<div bind:this={deliv} class="">
			{#if intersecting}
			<div>
			<div transition:fly={{ delay: 50, duration: 2500, x: 800, y: 0, opacity: 0.01, easing: quintOut }}
				class="text-2xl flex flex-col gap-6"
			>
					<p class="font-thin">
						(Deliverables)
					</p>
	
					<ul class="font-bold">
						<li>
							Brand identity
						</li>
						<li>
							Custom website design
						</li>
						<li>
							Full-Stack Website Development
						</li>
						<li>
							AI-Features Implementation
						</li>
						<li>
							Figma Prototypes
						</li>
					</ul>
			</div>
			</div>
			{/if}
		</div>
		</IntersectionObserver>

		<IntersectionObserver element={brief} let:intersecting>
			<div bind:this={brief} class="">
				{#if intersecting}
				<div>
				<div transition:fly={{ delay: 50, duration: 2500, x: 800, y: 0, opacity: 0.01, easing: quintOut }}
					class="text-2xl flex flex-col gap-6"
				>
						<p class="font-thin">
							(Brief)
						</p>
		
						<p class="font-bold">
							Create a platform for us and our clients that lets us manage multiple properties, multiple booking funnels (airbnb, booking.com, etc) and implement AI to help us run pricing analytics on autopilot as well as let us interact with the app, our bookings data and our clients through a chat interface.
						</p>

				</div>
				</div>
				{/if}
			</div>
		</IntersectionObserver>

		<IntersectionObserver element={solution} let:intersecting>
			<div bind:this={solution} class="">
				{#if intersecting}
				<div>
				<div transition:fly={{ delay: 50, duration: 2500, x: 800, y: 0, opacity: 0.01, easing: quintOut }}
					class="text-2xl flex flex-col gap-6"
				>
						<p class="font-thin">
							(Solution)
						</p>
		
						<p class="font-light">
							Founded in the rural Bavaria, Germany, HoRizen was able to 10x the revenue of their first client through manual leveraging of booking platforms, digital marketing and AI technologies.

							<br><br>
							After realising that their systems were facing a bottleneck through the need of manual human labor, we decided to partner up and build them a fully customised in-house platform for removing all unnecessary human interactions while still keeping experts in the loop.

							<br><br>
							Starting with a modern, elegant interface with bright orange to display the vitality of their brand and dark contrast to solidify the premium service they provide, we developed a platform that allowed them to handle bookings in a much more natural and intuitive way so their clients don’t get confused and they can offer a truly done-for-you experience.

							<br><br>
							Our platform enabled them to shorten their implementation time by 84% and increase their closing rate through the rebranded image.
						</p>

				</div>
				</div>
				{/if}
			</div>
		</IntersectionObserver>

	</div>
</div>

<div class="w-full h-full flex flex-row relative justify-start items-start ">
	<IntersectionObserver element={final} let:intersecting>
		<div bind:this={final} class="min-h-[60vh]">
		  {#if intersecting}
	
			<div transition:fly={{ delay: 0, duration: 3000, y: -600 }} class="pb-40 pt-20">
				<img src="/mockups/bkn.png" alt="booking" class=" scale-90 -ml-14 ">
			</div>
		{/if}
		</div>
	</IntersectionObserver>
</div>

<div class="w-full h-full min-h-[40vh] flex flex-row relative justify-center items-center overflow-hidden ">
	<IntersectionObserver element={cta} let:intersecting>
		<div bind:this={cta} class="w-full text-start flex justify-start px-8 md:px-20">
		  {#if intersecting}
	
			<a href="/apply" transition:fly={{ delay: 0, duration: 3000, x: 400 }} class="pb-40">
				<h3 class="text-6xl hover:text-8xl sm:text-8xl sm:hover:text-[120px] md:text-[140px] md:hover:text-[180px] xl:text-[200px] xl:hover:text-[250px] transition-all duration-300 ease-in-out font-black leading-none uppercase text-start">
					{@html $endcta}
				</h3>
			</a>
		{/if}
		</div>
	</IntersectionObserver>
</div>