<script>
// @ts-nocheck

    import InfiniteMovingCards from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingCards.svelte";
    import InfiniteMovingBoxes from "$lib/components/ui/InfiniteMovingCards/InfiniteMovingBoxes.svelte";
    import ContainerScrollAnimation from "$lib/components/ui/ContainerScrollAnimation/ContainerScrollAnimation.svelte";
    import { useTransform, useViewportScroll } from "svelte-motion";
    import GoogleGeminiEffect from "$lib/components/ui/GoogleGeminiEffect/GoogleGeminiEffect.svelte";
    import Spotlight from "$lib/components/ui/Spotlight/Spotlight.svelte";
    import Button from "$lib/components/ui/button/button.svelte";
    import TextGenerateEffect from "$lib/components/ui/TextGenerateEffect/TextGenerateEffect.svelte";
    import { fade, slide, scale } from 'svelte/transition';
	  import { onMount } from "svelte";
    import { calendly } from "../stores";

    const words = 'Bring your business to the world wide web'


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
      content: 'ASTRALTA ✱',
		},
		{
			quote:
				'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
			name: 'Jane Austen',
			title: 'Pride and Prejudice',
      content: 'ASTRALTA ✱',

		},
		{
			quote:
				'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.',
			name: 'Herman Melville',
			title: 'Moby-Dick',
      content: 'ASTRALTA ✱',
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

</script>


<!-- Praise the Lord -->


<div class="w-full h-full min-h-screen flex flex-col">
  <div
  class="relative min-h-screen flex flex-col items-center justify-center overflow-hidden rounded-md bg-white antialiased dark:bg-black dark:bg-grid-white/[0.05] lg:pt-[40vh] pt-[25vh]"
  >
  <div class="md:w-3/5 w-full px-8 h-full min-h-[40vh] flex">
    <TextGenerateEffect {words} />
  </div>

  <div>
    <InfiniteMovingBoxes items={cards} direction="left" speed="fast" />
  </div>

  <div class="pb-40 pt-10">
    <InfiniteMovingCards items={testimonials} direction="right" speed="normal" />
    <InfiniteMovingCards items={testimonials} direction="left" speed="normal" />
  </div>
  </div>

  <div class=" w-full h-full min-h-[60vh] flex flex-col md:flex-row px-6 md:px-10 lg:px-20 py-20">
    <div class="w-1/4 h-full pt-2 py-10 shrink-0">
      ✱ Welcome
    </div>
    <div class="w-auto h-full flex justify-start ">
      <div>
        <p class=" text-5xl md:text-7xl font-thin">
          We are a purpose-driven studio based in Munich, Germany - with expertise across branding, web design, web development and AI.
        </p>
  
        <div class="h-40 w-full flex flex-col md:flex-row py-10 mb-32 sm:mb-12">
          <div class="w-1/3 md:px-6 py-2">
            <span>
              (Approach)
            </span>
          </div>

          <div class="text-[#727272]">
            We help you find clarity in your message, and communicate that to your audience in an efficient way. We use purposeful design and consumer psychology to cut through the noise and put focus on your message. 
            <br> <br>
            Put simply, <b class="font-normal text-white">we make it easier for brands to communicate their vision</b>.
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
