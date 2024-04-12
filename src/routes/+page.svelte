<script>
// @ts-nocheck

    import IntersectionObserver from "svelte-intersection-observer";
    import InfiniteMovingCards from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingCards.svelte";
    import InfiniteMovingBoxes from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingBoxes.svelte";
    import * as Accordion from "$lib/components/ui/accordion/index.ts";
    import ContainerScrollAnimation from "$lib/components/ui/ContainerScrollAnimation/ContainerScrollAnimation.svelte";
    import { useTransform, useViewportScroll } from "svelte-motion";
    import GoogleGeminiEffect from "$lib/components/ui/GoogleGeminiEffect/GoogleGeminiEffect.svelte";
    import Spotlight from "$lib/components/ui/Spotlight/Spotlight.svelte";
    import Button from "$lib/components/ui/button/button.svelte";
    import TextGenerateEffect from "$lib/components/ui/TextGenerateEffect/TextGenerateEffect.svelte";
    import { fade, slide, scale, fly, blur } from 'svelte/transition';
	  import { onMount } from "svelte";
    import { quintOut, cubicInOut, quintInOut } from 'svelte/easing';
    import { calendly, footerColor } from "../stores";

    // const words = 'Bring your business to the world wide web'
    // const words = "Attract qualified customers and investors to your startup from the world wide web."
    // const words = "Attract clients for your business from the world wide web."
    const words = "Attract high-budget clients for your business from the world wide web."
    // brick and morter
    // Tech Startups#


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

        let show;
        $: show = false;

        onMount(() => {
            show = true;
            footerColor.set("bg-gradient-to-b from-[#6939F1] to-black")
        })

        let services = [
          {
            title: 'Full Product Delivery',
            url: '/services/fpd',
            active: true,
          },
          {
            title: 'Web Development',
            url: '/services/webdev',
            active: true,
          },
          {
            title: 'UI/UX',
            url: '/services/design',
            active: true,
          },
          {
            title: 'AI',
            url: '/services/ai',
            active: true,
          },
        ]
    
        const testimonials = [
		{
			quote:
				"To be, or not to be, that is the question: Whether 'tis nobler in the mind to suffer The slings and arrows of outrageous fortune, Or to take Arms against a Sea of troubles, And by opposing end them: to die, to sleep.",
			name: 'William Shakespeare',
			title: 'Hamlet',
      content: 'ASTRALTA ✱',
		},
		{
			quote: 'All that we see or seem is but a dream within a dream.',
			name: 'Edgar Allan Poe',
			title: 'A Dream Within a Dream',
      content: 'ASTRALTA ✱ ',
		},
		{
			quote:
				'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
			name: 'Jane Austen',
			title: 'Pride and Prejudice',
      content: 'ASTRALTA ✱ ' ,

		},
		{
			quote:
				'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.',
			name: 'Herman Melville',
			title: 'Moby-Dick',
      content: 'ASTRALTA ✱ ',
		}
	];


  const cards = [
		{
			quote:
				"To be, or not to be, that is the question: Whether 'tis nobler in the mind to suffer The slings and arrows of outrageous fortune, Or to take Arms against a Sea of troubles, And by opposing end them: to die, to sleep.",
			name: 'William Shakespeare',
			title: 'Hamlet',
      content: '/cards/01.png',
		},
		{
			quote: 'All that we see or seem is but a dream within a dream.',
			name: 'Edgar Allan Poe',
			title: 'A Dream Within a Dream',
      content: '/cards/02.png',
		},
		{
			quote:
				'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
			name: 'Jane Austen',
			title: 'Pride and Prejudice',
      content: '/cards/03.png',

		},
		{
			quote:
				'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.',
			name: 'Herman Melville',
			title: 'Moby-Dick',
      content: '/cards/04.png',
		},
    {
			quote:
				'It is a truth acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
			name: 'Jane MCArthur',
			title: 'Pride and Prejudice 2',
      content: '/cards/05.png',

		},


	];


  let maincta;
  let flow;
  let vision;
  let boxes;
  let workt;
  let outcomes;
  let test;
  let header;
  let sparkles;
  let workHeader;
  let leftcol;
  let rightcol;
  let testimonial;
  let faqs;
  let p1;
  let p2;

  // flow
  let step1;
  let step2;
  let step3;


const bluredClass = "scale-90 hover:scale-100 blur-sm hover:blur-0 transition-all duration-300 ease-in-out"
const biggerClass = "scale-90 hover:scale-95 transition-all duration-300 ease-in-out"
</script>


<!-- Praise the Lord -->




<div class="w-full h-full min-h-screen flex flex-col">
  <div
  class="relative min-h-screen flex flex-col items-center justify-center overflow-hidden rounded-md bg-white antialiased dark:bg-black dark:bg-grid-white/[0.05] lg:pt-[25vh] pt-[25vh]"
  >
  <div class="w-full px-8 h-full min-h-[40vh] flex flex-col">
    <div class="md:w-4/5 w-full sm:px-8 md:px-10 lg:px-20">
      <TextGenerateEffect {words} />
      <div class="w-full h-full flex pb-20">
        <IntersectionObserver element={maincta} let:intersecting>
          <div bind:this={maincta}>
            {#if intersecting}
            <div
            transition:fly={{ delay: 300, duration: 3000 }}
              >
              <Button href="/apply" class="bg-transparent my-2 border-2 border-white border-opacity-40 text-lg md:text-xl rounded-full px-12 py-2 hover:text-black hover:px-16 md:hover:px-40 transition-all duration-300 ease-in-out text-white">
                Start with a free strategy call
              </Button>
            </div>
            {/if}
          </div>
        </IntersectionObserver>
        
      </div>
      
    </div>

    <IntersectionObserver element={sparkles} let:intersecting>
      <div bind:this={sparkles}>
        {#if intersecting}
          <div 
            transition:fly={{ delay: 100, duration: 2000 }}
            class="w-full font-semibold text-2xl h-12 flex flex-row justify-between px-8 opacity-100"
            >
            <span class="flex items-center justify-center">
              +
            </span>
            <span class="flex items-center justify-center">
              +
            </span>
            <span class="flex items-center justify-center">
              +
            </span>
            <span class="flex items-center justify-center">
              +
            </span>
          </div>
        {/if}
      </div>
    </IntersectionObserver>
  </div>
  
  <div class="py-24 hidden">
    <InfiniteMovingBoxes items={cards} direction="left" speed="fast" />
  </div>

  <IntersectionObserver element={boxes} let:intersecting>
    <div bind:this={boxes} class="min-h-[70vh]">
      {#if intersecting}

        <div transition:fly={{ delay: 0, duration: 3000, y: -1200 }} class="py-20">
          <InfiniteMovingCards items={testimonials} direction="right" speed="slow" />
          <InfiniteMovingCards items={testimonials} direction="left" speed="slow" />
        </div>

      {/if}
    </div>
  </IntersectionObserver>

  <div class="h-full min-h-[80vh] md:min-h-[90vh] flex flex-col justify-center items-center  w-4/5">
    <IntersectionObserver element={vision} let:intersecting>
      <div bind:this={vision}>
        {#if intersecting}
          <div
            transition:fly={{ delay: 0, duration: 2000, y: -1200 }}
            >
            <span class="text-4xl md:text-6xl font-extralight text-[#727272]">
              You deserve a <b class="text-white font-thin">business that grows on its own terms</b>.
              <br>
              <br>
              Consistent high-budget clients and high conversion rates shouldn’t be the exception — <b class="text-white font-thin">they should be your standard</b>.
            </span>
          </div>
        {/if}
        </div>
      </IntersectionObserver>
  </div>


  </div>

  <div class=" w-full h-full min-h-[60vh] flex flex-col md:flex-row px-6 md:px-10 lg:px-20 pb-40 overflow-hidden">
    <div class=" w-full h-full flex flex-col md:px-8 py-10 md:py-0">
      <div class="w-1/4 h-full pt-2 py-10 shrink-0">
        ✱ Welcome
      </div>
      <div class="w-full justify-start items-start flex h-full">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="/content/reg.JPG" alt="register image" class="rounded-2xl w-4/5 flex">
      </div>
    </div>

    <div class="w-auto h-full flex justify-start min-h-screen md:min-h-[60vh]">
      <IntersectionObserver element={header} let:intersecting>
        <div bind:this={header}>
          {#if intersecting}
          <div>
            <div transition:fly={{ delay: 50, duration: 2500, x: 800, y: 0, opacity: 0.01, easing: quintOut }}>
              <p class=" text-5xl md:text-7xl font-thin text-[#868686]">
                We are a <b class="text-white font-thin">purpose-driven software studio</b> based in Munich, Germany - with expertise across <b class="text-white font-thin">storytelling</b>, <b class="text-white font-thin">web design</b>, <b class="text-white font-thin">brand strategy</b> and <b class="text-white font-thin">AI</b>.
              </p>
        
              <div class="h-40 w-full flex flex-col md:flex-row py-10 mb-32 sm:mb-12">
                <div class="w-1/3 md:px-6 py-2">
                  <span>
                    (Approach)
                  </span>
                </div>
      
                <div transition:fly={{ delay: 250, duration: 2000, x: 800, y: 0, opacity: 0.1, easing: quintOut }} class="text-[#868686]">
                  Every business owner deserves to feel comfortable and confident about their brand and vision, regardless of the stage of the business. 
                  <br>
                  <br>
                  We help you with the feeling of not having enough time to prioritise development or business growth because you feel stuck in acquiring new customers. 

                  <br>
                  Get rid off overwhelming business advice online that lacks personalised guideliness or a clear plan to follow. We've taken care of each major and minor step for you.

                  <!-- We help you define clarity in your message and vision. Then we communicate that to your audience through visuals, interactions and experiences that align to your business strategy. For you this means greater percieved value of your brand and your business, which directly translates into more suitable and higher-paying clients that resonate with your product. -->
                  <!-- We help you find clarity in your message, and communicate that to your audience in an efficient way. We use purposeful design and consumer psychology to cut through the noise and put focus on your message.  -->
                  <br> <br>
                  <!-- Put simply, <b class="font-normal text-white">we make it easier for your customers to understand the value of your product. </b>. -->
                  Put simply, <b class="font-normal text-white">you shouldn't have to struggle to make your customers understand the value of your product</b>.
                </div>
              </div>
            </div>
          </div>
          {/if}
        </div>
      </IntersectionObserver>
    </div>
  </div>
</div>


<!-- HERE IS WHERE WE SHOWCASE SOME OF OUR WORK!!! -->

<div class="w-full h-full flex flex-col">
  <div class=" w-full h-full min-h-[60vh] flex flex-col md:flex-row-reverse px-6 md:px-10 lg:px-20 pb-40 justify-center items-center overflow-hidden">
    <div class="w-auto h-full flex min-h-screen md:min-h-[60vh] justify-center items-center">

      <IntersectionObserver element={outcomes} let:intersecting>
        <div bind:this={outcomes}>
          {#if intersecting}
          <div>
            <div transition:fly={{ delay: 0, duration: 2500, x: 0, y: -800, opacity: 0.01, easing: quintOut }}>
              <div class="w-full text-center py-4">
                <span>
                  (Our Mision)
                </span>
              </div>
              <p class=" text-5xl md:text-7xl font-thin text-[#868686] text-center lg:px-40">
                You feel <b class="text-white font-thin">confident and proud about your business</b> with a <b class="text-white font-thin">clear message</b>, <b class="text-white font-thin">consistent design</b>, <b class="text-white font-thin">proven growth strategies</b> and <b class="text-white font-thin">online presence</b>.
              </p>
            </div>
          </div>
          {/if}
        </div>
      </IntersectionObserver>
    </div>
  </div>
</div>

<div class="bg-black w-full h-full flex flex-col px-6 md:px-10 lg:px-20 justify-start items-center overflow-hidden">
  <div class=" w-full md:min-h-[50vh] min-h-[20vh]">
    <IntersectionObserver element={flow} let:intersecting>
      <div bind:this={flow} class="">
        {#if intersecting}
        <div
        transition:fly={{ delay: 10, duration: 1500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
          >
          <span>
            (How we get you there)
          </span>
          <h2 class="w-full text-9xl md:text-[200px] lg:text-[300px] xl:text-[400px] text-white font-bold uppercase flex">
            Flow
          </h2>
        </div>
        {/if}
        </div>
      </IntersectionObserver>
  </div>
  <!-- Step 1 -->
  <div class="w-full h-full py-6 min-h-[80vh]">
    <div class="w-full flex flex-row">
      <div class="w-1/4">
        <span class="text-8xl">
          1
        </span>
      </div>
      <div class="w-3/4">
        <IntersectionObserver element={step1} let:intersecting>
          <div bind:this={step1} class="">
            {#if intersecting}
            <div class="w-full flex flex-col h-full gap-10"
              transition:fly={{ delay: 10, duration: 1500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
            >
              <span class="text-5xl md:text-8xl">
                Start for free
              </span>
      
              <div class="w-full h-full flex flex-row justify-end">
                <p class="text-[#868686] md:w-2/3 w-full">
                  Start with our <b class="font-light text-white">free brand strategy session</b> to help you take small steps towards feeling more confident and secure about your business' intentions and vision. You will get an initial set of brand strategy guidelines which we will use to later develop your website and brand identity.
                </p>
              </div>
      
              <div class="w-full h-full flex md:flex-row flex-col">
                <div class="md:w-1/3 w-full">
                  <span>
                    (What you do)
                  </span>
                </div>
      
                <div class="w-auto">
                  <p class="text-[#868686]">
                    Apply for a free session <a href="/apply" class="text-white opacity-80 hover:opacity-100 transition-all duration-300 ease-in-out">→ here</a>
                  </p>
                </div>
              </div>
      
              <div class="w-full">
                <img src="/content/bsg.png" alt="bsg" class="rounded-2xl">
              </div>
            </div>
            {/if}
          </div>
        </IntersectionObserver>
      </div>


    </div>
  </div>

  <!-- Step 2 -->
  <div class="w-full h-full py-6 min-h-screen">
    <div class="w-full flex flex-row">
      <div class="w-1/4">
        <span class="text-8xl">
          2
        </span>
      </div>
      <div class="w-3/4">
        <IntersectionObserver element={step2} let:intersecting>
          <div bind:this={step2} class="">
            {#if intersecting}
            <div class="w-full flex flex-col h-full gap-10"
              transition:fly={{ delay: 10, duration: 1500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
            >
            <span class="text-5xl md:text-8xl">
                Select a programme
              </span>
      
              <div class="w-full h-full flex flex-row justify-end">
                <p class="text-[#868686] md:w-2/3 w-full">
                  Pick a programme that best fits your business and get <b class="text-white font-light">step-by-step guidance to get your business www-ready</b>. 
                  
                  <br>
                  <br>

                  From here onwards we will explore your business deeply to clearly understand the value of your product or services so we can create a strong clear website for your business. If your customers understand clearly what you offer, they can have the right expectations and are more likely to be satisfied with your services and leave great reviews.
                </p>
              </div>
      
              <div class="w-full h-full flex md:flex-row flex-col">
                <div class="md:w-1/3 w-full">
                  <span>
                    (What you do)
                  </span>
                </div>
      
                <div class="md:w-2/3 w-full">
                  <p class="text-[#868686]">
                    Help us understand your vision and product. 
                  </p>
                  <br>

                  <p class="text-[#868686]">
                    Sit down and relax as you enjoy our <b class="text-white font-light">Done-For-You</b> service towards building a strong brand and a business that grows swiftly.
                  </p>

                </div>
              </div>
      
              <div class="w-full">
                <img src="/content/w.png" alt="w" class="rounded-2xl">
              </div>
            </div>
            {/if}
          </div>
        </IntersectionObserver>
      </div>


    </div>
  </div>


  <!-- Step 3 -->
  <div class="w-full h-full py-6 min-h-screen">
    <div class="w-full flex flex-row">
      <div class="w-1/4">
        <span class="text-8xl">
          3
        </span>
      </div>
      <div class="w-3/4">
        <IntersectionObserver element={step3} let:intersecting>
          <div bind:this={step3} class="">
            {#if intersecting}
            <div class="w-full flex flex-col h-full gap-10"
              transition:fly={{ delay: 10, duration: 1500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
            >
            <span class="text-5xl md:text-8xl">
                Watch it grow
              </span>
      
              <div class="w-full h-full flex flex-row justify-end">
                <p class="text-[#868686] md:w-2/3 w-full">
                  Keep at it and watch as you <b class="font-light text-white">attract high-budget leads</b> that are <b class="font-light text-white">easier to close</b> and <b class="font-light text-white">easier to fulfill</b>. We'll be there for you along the way. 
                  
                  <br>
                  <br>

                  Become part of a community of business owners, leaders and startup founders that constantly support each other towards smart growth.
                </p>
              </div>
      
              <div class="w-full h-full flex md:flex-row flex-col">
                <div class="md:w-1/3 w-full">
                  <span>
                    (What you do)
                  </span>
                </div>
      
                <div class="md:w-2/3 w-full">
                  <p class="text-[#868686]">
                    Grab a drink and celebrate your peace.
                  </p>

                </div>
              </div>
      
              <div class="w-full">
                <img src="/content/car.png" alt="car" class="rounded-2xl">
              </div>
            </div>
            {/if}
          </div>
        </IntersectionObserver>
      </div>


    </div>
  </div>

</div>


<div class="bg-black w-full h-full flex flex-col px-6 md:px-10 lg:px-20 justify-start items-center overflow-hidden py-20">
  <div class=" w-full md:min-h-[50vh] min-h-[20vh]">
    <IntersectionObserver element={workt} let:intersecting>
      <div bind:this={workt} class="">
        {#if intersecting}
        <div
        transition:fly={{ delay: 10, duration: 1500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
          >
          <span>
            (Sample)
          </span>
          <h2 class="w-full text-9xl md:text-[200px] lg:text-[300px] xl:text-[400px] text-white font-bold uppercase flex">
            work
          </h2>
        </div>
        {/if}
        </div>
      </IntersectionObserver>
  </div>

  <!-- Portfolio Posters -->
  <div class="w-full">
    <div class="w-full h-full flex flex-col lg:flex-row gap-10 justify-center items-start">
      <IntersectionObserver element={leftcol} once={true} let:intersecting>
        <div bind:this={leftcol} class="">
          {#if intersecting}
          <div 
          transition:fly={{ delay: 50, duration: 1500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
            class="w-full h-full flex flex-col gap-10">
            <div>
              <a href="/projects/horizen" class="">
                <img src="/posters/hrzn.png" alt="hrzn" class="{biggerClass}">
              </a>

              <div class="px-20 flex flex-col gap-2">
                <span class="uppercase">
                  HoRizen 
                </span>
                <span>
                  (Web App, Brand, AI)
                </span>
              </div>
            </div>

            <div>
              <a href="/projects/portfolio" class="">
                <img src="/posters/me.png" alt="ad" class="{biggerClass}">
              </a>

              <div class="px-20 flex flex-col gap-2">
                <span class="uppercase">
                  Personal Website
                </span>
                <span>
                  (Web design, Brand, AI)
                </span>
              </div>
            </div>

            </div>
            {/if}
        </div>
      </IntersectionObserver>

      <IntersectionObserver element={rightcol} once={true} let:intersecting>
        <div bind:this={rightcol}>
          {#if intersecting}
          <div 
          transition:fly={{ delay: 50, duration: 1500, x: 600, y: 0, opacity: 0.01, easing: quintOut }}
            class="w-full h-full flex flex-col gap-10 lg:mt-40">
            <div>
              <a href="/projects/aivery" class="">
                <img src="/posters/aiv.png" alt="ai" class="{biggerClass}">
              </a>

              <div class="px-20 flex flex-col gap-2">
                <span class="uppercase">
                  Aivery
                </span>
                <span>
                  (AI, Brand, MVP, Startup)
                </span>
              </div>
            </div>
    
            <div>
              <a href="/projects/studio" class="">
                <img src="/posters/st.png" alt="st" class="{biggerClass}">
              </a>

              <div class="px-20 flex flex-col gap-2">
                <span class="uppercase">
                  Astralta
                </span>
                <span>
                  (Web App, AI, SaaS)
                </span>
              </div>
            </div>
            </div>
          {/if}
        </div>
      </IntersectionObserver>
    </div>
  </div>
</div>

<div class="bg-black w-full h-full flex flex-col px-6 md:px-10 lg:px-20 justify-start items-center overflow-hidden">
  <div class=" w-full h-full min-h-[140vh] md:min-h-[90vh] flex flex-col md:flex-col px-6 md:px-10 lg:px-20 justify-center items-center overflow-hidden">
    <div class="w-full h-full pt-2 py-10 shrink-0 text-start">
      (What people say)
    </div>
    <div class="">
      <IntersectionObserver element={test} let:intersecting>
        <div bind:this={test} class="">
          {#if intersecting}
          <div
          transition:fly={{ delay: 50, duration: 2500, x: 600, y: 0, opacity: 0.01, easing: quintOut }}
            >
            <div>
              <p class=" text-5xl md:text-7xl font-thin">
                "Outstanding high-quality service and deliverables. The collaboration was great, and the final result was top-notch. Definitely recommend it."
              </p>
            </div>
            <div class="text-white opacity-50 text-xl font-thin py-8">
              Co-Founder - HoRizen
            </div>
            </div>
          {/if}
          </div>
        </IntersectionObserver>
    </div>
  </div>
</div>

<div class="bg-black w-full h-full flex flex-col px-6 md:px-10 lg:px-20 justify-start items-center overflow-hidden">
  <div class=" w-full h-full min-h-[120vh] md:min-h-[90vh] flex flex-col md:flex-row px-6 md:px-10 lg:px-20 overflow-hidden justify-center items-start">
    <div class="md:w-1/4 w-full h-full pt-2 shrink-0">
      ✱ Frequently Asked Questions
    </div>

    <div class="w-full min-h-[70vh] flex items-start flex-col justify-center">
      <IntersectionObserver element={faqs} let:intersecting>
        <div bind:this={faqs}>
          {#if intersecting}
          <div
          transition:fly={{ delay: 50, duration: 2500, x: -600, y: 0, opacity: 0.01, easing: quintOut }}
            >
            <Accordion.Root class="w-full text-xl min-w-[60vw]">
              <Accordion.Item value="item-1" class="py-6">
                <Accordion.Trigger class="text-xl text-start">What should I expect when starting a project?</Accordion.Trigger>
                <Accordion.Content
                  class="text-[#9c9c9c] text-xl font-light"  
                >
                  Once you've submitted the <a href="/apply" class="text-white italic opacity-80 hover:opacity-100 transition-all duration-0 ease-in-out">application form</a>, we'll meet with you to guide you through each step of the development process.
                  </Accordion.Content
                >
              </Accordion.Item>
              <Accordion.Item value="item-2" class="py-6">
                <Accordion.Trigger class="text-xl text-start">How long does a project take?</Accordion.Trigger>
                <Accordion.Content
                  class="text-[#9c9c9c] text-xl font-light"  
                >
                  Most of the projects take between 1-3 months. Single-page websites can take between 2-4 weeks.
                  </Accordion.Content
                >
              </Accordion.Item>
              <Accordion.Item value="item-3" class="py-6">
                <Accordion.Trigger class="text-xl text-start">How much does a project cost?</Accordion.Trigger>
                <Accordion.Content
                  class="text-[#9c9c9c] text-xl font-light"  
                >
                  <!-- We charge a simple project fee, depending on scope of work. Most of our web design projects range between $4,000 for a single landing page, to $20,000 for a complex, multipage CMS site. We don't offer hourly work. SaaS development starts at $25.000. -->
                  We charge a simple project fee depending on scope of work. Most of our web design projects range between $3,000 for a one-page website, to $15 000 for a complex, multipage CMS site. We don't offer hourly work. 
                  </Accordion.Content
                >
              </Accordion.Item>
              <Accordion.Item value="item-4" class="py-6">
                <Accordion.Trigger class="text-xl text-start">What are the payment terms for a project?</Accordion.Trigger>
                <Accordion.Content
                  class="text-[#9c9c9c] text-xl font-light"  
                >
                  50% upfront and 50% after launch. We also offer custom pricing plans on a case-by-case basis. This is all discussed in our first meeting.
                  </Accordion.Content 
                >
              </Accordion.Item>
              <Accordion.Item value="item-5" class="py-6">
                <Accordion.Trigger class="text-xl text-start">Do you require finalized designs when reaching out?</Accordion.Trigger>
                <Accordion.Content
                  class="text-[#9c9c9c] text-xl font-light"  
                >
                  No - we can definitely use whatever you might already have but we offer a Done-For-You service at the core. Meaning we'll take care of each and every step required to the completion of your project.
                  </Accordion.Content
                >
              </Accordion.Item>
            </Accordion.Root>
          </div>
          {/if}
        </div>  
      </IntersectionObserver>
    </div>
  </div>
</div>