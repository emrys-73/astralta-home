<script lang="ts">
// @ts-nocheck

    import { cn } from "$lib/utils";
    import { onMount } from "svelte";
    export let items;
    export let direction = "left";
    export let speed = "fast";
    export let pauseOnHover = false;
    export let className = void 0;
    let containerRef;
    let scrollerRef;
    onMount(() => {
      addAnimation();
    });
    let start = false;
    function addAnimation() {
      if (containerRef && scrollerRef) {
        const scrollerContent = Array.from(scrollerRef.children);
        scrollerContent.forEach((item) => {
          const duplicatedItem = item.cloneNode(true);
          if (scrollerRef) {
            scrollerRef.appendChild(duplicatedItem);
          }
        });
        getDirection();
        getSpeed();
        start = true;
      }
    }
    const getDirection = () => {
      if (containerRef) {
        if (direction === "left") {
          containerRef.style.setProperty("--animation-direction", "forwards");
        } else {
          containerRef.style.setProperty("--animation-direction", "reverse");
        }
      }
    };
    const getSpeed = () => {
      if (containerRef) {
        if (speed === "fast") {
          containerRef.style.setProperty("--animation-duration", "20s");
        } else if (speed === "normal") {
          containerRef.style.setProperty("--animation-duration", "40s");
        } else {
          containerRef.style.setProperty("--animation-duration", "80s");
        }
      }
    };
    </script>
    
    <div
        bind:this={containerRef}
        class={cn(
            'scroller relative z-20 max-w-[99vw] overflow-hidden text-white dark:text-gray-100 [mask-image:linear-gradient(to_right,transparent,white_60%,white_80%,transparent)]',
            className
        )}
    >
        <ul
            bind:this={scrollerRef}
            class={cn(
                ' flex w-max min-w-full shrink-0 flex-nowrap leading-none ',
                start && 'animate-scroll ',
                pauseOnHover && 'hover:[animation-play-state:paused]'
            )}
        >
            {#each items as item, idx (item.name)}

                    <div class="w-full">
                      <h2 class="text-9xl md:text-[300px] font-bold">
                        {item.content}
                      </h2>

                    </div>
            {/each}
        </ul>
    </div>