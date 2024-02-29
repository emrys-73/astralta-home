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

    const calendlyURL = 'https://calendly.com/adrian_cal/meet'

    const words = 'Your dream idea into software in 14 days or its free.'


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
    

</script>


<!-- <div
	class="flex h-full min-h-screen w-full flex-col items-center justify-center overflow-hidden rounded-md bg-white antialiased bg-transparent dark:bg-transparent dark:bg-grid-white/[0.05]"
>
	<InfiniteMovingCards items={testimonials} direction="right" speed="slow" />
</div> -->

<!-- {#if show} -->
<div class=" bg-gradient-to-b from-transparent to-black">
    <div
        transition:scale={{ delay: 0, duration: 700 }} 
        class="flex h-full min-h-[90vh] overflow-hidden rounded-md px-4 antialiased  md:items-center md:justify-center z-10"
        >
        <Spotlight className="-top-40 left-0 md:left-60 md:-top-20" fill="white" />
        {#if show}
        <div
            transition:scale={{ delay: 100, duration: 2700 }} 
            class="absolute top-0 right-0 w-3/4 overflow-hidden h-full justify-end items-center md:flex hidden"
         >
                <img src="/boom.png" alt="boom" class="-mr-20 opacity-30">
            </div>
        {/if}
        {#if show}
        <div
            class="absolute top-0 right-0 w-3/4 h-full justify-end items-center md:flex hidden"
         >
                <div class=" bg-gradient-to-r from-transparent to-black w-full h-full opacity-80"/>
            </div>
        {/if}
        {#if show}
          <div 
            transition:scale={{ delay: 100, duration: 700 }} 
            class="w-1/3 h-full min-h-60 min-w-40 absolute right-0 top-0 hidden md:flex"
            >
            <div class="w-full h-full flex-col justify-center px-12 gap-4 mt-2 items-end z-30 hidden">
              {#each services as s}
              <Button href={s.url} class="bg-[#FFF] rounded-full hover:text-black hover:px-8 px-6 bg-opacity-10 opacity-80 backdrop-blur-md border-[0.5px] hover:opacity-100 transition-all ease-in-out duration-500 text-white font-semibold">
                {s.title}
              </Button>
              <!-- <Button href={s.url} class="bg-[#FFF] bg-opacity-10 opacity-100 backdrop-blur-md border-[0.5px] hover:opacity-100 transition-all ease-in-out duration-500 text-white font-semibold border-[#B3AC9F] border-opacity-60 hover:text-black">
                {s.title}
              </Button> -->
              {/each}
            </div>
          </div>
        {/if}

        <div class=" relative justify-start flex flex-col items-start z-10 mx-auto w-full p-4 pt-20 md:pt-0 gap-4 md:gap-8 lg:pl-10">
            <div class="md:w-3/4 py-2 pr-20 xl:pr-32 flex flex-col">
                {#if show}
                    <p 
                        transition:fade={{ delay: 4100, duration: 2000 }}  
                        class="uppercase text-xl text-[#B3AC9F]"
                    >
                        Astralta
                    </p>
                {/if}
                <h1
                    class="bg-opacity-50 bg-gradient-to-b from-neutral-50 to-neutral-400 bg-clip-text text-4xl font-bold text-transparent md:text-6xl"
                >
                    <TextGenerateEffect {words} />
                </h1>
            </div>

            {#if show}
                <div
                    transition:fade={{ delay: 2800, duration: 2000 }}  
                    class="w-full md:w-2/5 lg:w-1/2 py-2 z-40 flex flex-col "
                >
                    <p class="flex mx-auto text-base justify-start w-full font-normal text-neutral-300 opacity-70 md:opacity-100">
                      <!-- We are a Design-Driven Software Studio with a worldwide pool of experts ready to build groundbreaking Done-For-You Software powered by AI. -->
                      We are a design-driven software studio offering a pool of worldwide experts ablte to build groundbreaking software powered by AI.
                  </p>
                  <p class="opacity-40">
                    Based in Munich, Germany
                  </p>
                </div>
            {/if}

            {#if show}
              <div 
                  transition:fade={{ delay: 3100, duration: 2000 }}  
                  class="py-5 w-full flex flex-col gap-4 z-40"
              >
              
              <div class="w-full h-full flex-row flex-wrap gap-2 z-50 hidden">
                {#each services as s}
                <Button href={s.url} class="bg-[#FFF] bg-opacity-10 opacity-50 backdrop-blur-md border-[0.5px] hover:opacity-100 transition-all ease-in-out duration-300 text-white font-semibold border-[#B3AC9F] border-opacity-60 hover:text-black">
                  {s.title}
                </Button>
                {/each}
              </div>

              <Button href={calendlyURL} class="bg-[#716c5d] rounded-full z-40 flex w-full backdrop-blur-lg sm:w-min hover:px-20 transition-all ease-in-out duration-500 text-white hover:text-black">
                  <span class="flex font-semibold px-12">Start here</span>
              </Button>
              </div>
            {/if}

            {#if show}
              <!-- Hidden -->
              <div
                  transition:scale={{ delay: 4500, duration: 1200 }} 
                  class="absolute hidden left-0 z-0 w-full h-full justify-center items-center md:hidden"
              >

                <img src="/boom.png" alt="boom" class="-mr-20 opacity-60">
              </div>
            {/if}

           
        </div>
    </div>
<!-- 
    <div>
       What we do
    </div>

    <div>
      How we do it
    </div>

    <div>
      Why we do it
    </div>

    <div>
      Our story
    </div> -->



    <div class="w-full h-full flex flex-col gap-4 justify-start items-center pb-60 z-50">
      <span class="opacity-40">
          our services
      </span>

      <div class="w-full h-full flex flex-row gap-2 justify-center items-center flex-wrap z-50">
          {#each actionButtons as s}
              {#if s.active}
                  <Button href={s.url} class="bg-white bg-opacity-10 rounded-full px-6 hover:px-12 hover:text-black transition-all duration-300 text-white ease-in-out">
                      {s.title}
                  </Button>
              {/if}
          {/each}
      </div>
  </div>

</div>

<!-- {/if} -->




<!-- <div class="flex flex-col overflow-hidden">
	<ContainerScrollAnimation {users}>
		<h1 slot="titleComponent" class="text-4xl font-semibold text-black dark:text-white">
			Unleash the power of <br />
			<span class="mt-1 text-4xl font-bold leading-none md:text-[6rem]"> Scroll Animations </span>
		</h1>
	</ContainerScrollAnimation>
</div> -->
