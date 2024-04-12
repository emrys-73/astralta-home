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
            footerColor.set("bg-gradient-to-b from-[#71FF5F] to-[#5EE2FF]")
        })
    
        let header;
    
        const testimonials = [
            {
                quote:
                    "To be, or not to be, that is the question: Whether 'tis nobler in the mind to suffer The slings and arrows of outrageous fortune, Or to take Arms against a Sea of troubles, And by opposing end them: to die, to sleep.",
                name: 'William Shakespeare',
                title: 'Hamlet',
          content: 'PERSONAL SITE ✱',
            },
            {
                quote: 'All that we see or seem is but a dream within a dream.',
                name: 'Edgar Allan Poe',
                title: 'A Dream Within a Dream',
          content: 'PERSONAL SITE ✱',
            },
            {
                quote:
                    'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
                name: 'Jane Austen',
                title: 'Pride and Prejudice',
          content: 'PERSONAL SITE ✱' ,
    
            },
            {
                quote:
                    'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.',
                name: 'Herman Melville',
                title: 'Moby-Dick',
          content: 'PERSONAL SITE ✱',
            }
        ];
    
        let mainmockup;
        let headline;

        let mocks;
    
    
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

    
    <div class=" w-full h-full flex flex-col md:flex-row px-6 md:px-10 lg:px-20 bg-black overflow-hidden  justify-center items-start md:py-[10vh] lg:pt-[20vh]">
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
                        We wanted to build an impactful personal website with short compelling copy and an integrated AI Assistant taking care of all interactions.

                        <br>
                        <br>

                        The site became a successful part of the funnel doubling the client’s closing rate and ensuring a solid online presence that made networking and communicating their story and vision simpler than ever.
                    </p>
            
                </div>
                </div>
                {/if}
            </div>
            </IntersectionObserver>
        </div>
    </div>


    <div class="w-full h-full min-h-[60vh] flex justify-center items-center">
        <IntersectionObserver element={mocks} let:intersecting>
            <div bind:this={mocks} class="">
                {#if intersecting}
                <div>
                <div transition:fly={{ delay: 50, duration: 2500, y: -800, opacity: 0.01, easing: quintOut }}
                    class="text-2xl flex flex-col gap-6"
                >
                    <img src="/posters/me.png" alt="mockup" class="scale-75">
                    </div>
                </div>
                {/if}
                </div>
                </IntersectionObserver>
    </div>
    
    
    <div class=" w-full h-full min-h-[120vh] flex flex-col md:flex-row px-6 md:px-10 lg:px-20 bg-black overflow-hidden py-[20vh]">
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
                                Full-Stack Website Development
                            </li>
                            <li>
                                AI-Features Implementation
                            </li>
                            <li>
                                UI/UX Design
                            </li>
                            <li>
                                Copywriting
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
                                Create a personal website including personal branding from scratch with clear Call-To-Action Buttons to book calls and an integrated AI Assistant to handle all questions related to the person. The site must be responsive and easily skimmable. 
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
                                Adrian’s vision for this site is to convey simplicity and elegance through few bright impactful colours. Animations along the website should give the user a sense of calmness that combined with brief yet precise copy, end up transmitting his story within a few seconds of skimming through the page.

                                <br>
                                <br>

                                We took care of showcasing the personal brand identity through a custom logo as well as custom Memoji’s to direct the viewer’s attention throughout the site. 
                                
                                <br>
                                <br>
                                
                                The site was optimised for all screen sizes and all major browsers to ensure seamless interactions from anywhere in the world. 
                                
                                
                            </p>
    
                    </div>
                    </div>
                    {/if}
                </div>
            </IntersectionObserver>
    
        </div>
    </div>
    
    <div class="w-full h-full min-h-[60vh] flex flex-row relative justify-center items-center overflow-hidden ">
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