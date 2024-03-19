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
            footerColor.set("bg-gradient-to-b from-[#0CBE66] to-black")
        })
    
        let header;
    
        const testimonials = [
            {
                quote:
                    "To be, or not to be, that is the question: Whether 'tis nobler in the mind to suffer The slings and arrows of outrageous fortune, Or to take Arms against a Sea of troubles, And by opposing end them: to die, to sleep.",
                name: 'William Shakespeare',
                title: 'Hamlet',
          content: 'AIVERY ✱',
            },
            {
                quote: 'All that we see or seem is but a dream within a dream.',
                name: 'Edgar Allan Poe',
                title: 'A Dream Within a Dream',
          content: 'AIVERY ✱',
            },
            {
                quote:
                    'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.',
                name: 'Jane Austen',
                title: 'Pride and Prejudice',
          content: 'AIVERY ✱' ,
    
            },
            {
                quote:
                    'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.',
                name: 'Herman Melville',
                title: 'Moby-Dick',
          content: 'AIVERY ✱',
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
    
    <div class="w-full h-full md:min-h-[110vh] min-h-[50vh] sm:min-h-[70vh] flex flex-col justify-center items-center">
        <IntersectionObserver element={mainmockup} let:intersecting>
            <div bind:this={mainmockup} class="">
                {#if intersecting}
    
                <div
                    transition:fly={{ delay: 2, duration: 2500, y: -800 }} 
                    class=""
                >
                    <img src="/mockups/aivery_bento.png" alt="aiveryone" class=" scale-150 ml-40 md:scale-100 md:ml-0">

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
                        Aivery is an AI-powered software platform that enhances the steps of the sales acquisition pipeline through automation, sentiment analysis and data classification

                        <br><br>
                        The AI-Startup reached the Final Pitch of the accelerator program it was born in and generated traction through hundreds of interactions with the funnels and digital content we created for it.
                    </p>
            
                </div>
                </div>
                {/if}
            </div>
            </IntersectionObserver>
        </div>
    </div>
    
    <div class="w-full h-full flex flex-col px-20 min-h-[30vh] sm:min-h-[40vh] lg:min-h-[40vh]">
        <img src="/mockups/aivery_logo.png" alt="aivery_logo" class="shrink-0 md:scale-50 scale-75">
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
                                Brand identity
                            </li>
                            <li>
                                MVP Prototyping
                            </li>
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
                                Create a testable MVP that gathers data from prospects, researches automatically more about them, analyses compatibility with a product to be sold and generates scripts to approach said prospects through custom messages. Furthermore, make it so we never run out fo prospects because every run, the system finds, qualifies and recommends at least 3 more candidates.
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
                                Aivery was born at the heart of innovation in Munich, Germany. Through multiple iterations inside the startup accelerator program it was in, Aivery developed a unique essence for simplicity. We took that towards creating a brand identity that resonates with the modern albeit simple approach of Aivery towards building tech.

                                <br>
                                <br>

                                The design and MVP was tested exhaustively during demo calls in a way that it got improved more and more as the company got more consolidated. All design tasks were soon taken care of and we built a Framer Website as well as the Full-Stack MVP for the software itself.
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