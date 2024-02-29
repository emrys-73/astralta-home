<script lang="ts">
// @ts-nocheck

    import { Motion } from "svelte-motion";
    import { cn } from "$lib/utils";
    export let words;
    export let className = void 0;
    const variants = {
      visible: (i) => ({
        opacity: 1,
        transition: {
          delay: i * 0.2,
          duration: 2
        }
      }),
      hidden: { opacity: 0 }
    };
    </script>
    
    <div class={cn('font-bold', className)}>
        <div class="mt-4">
            <div class=" bg-opacity-50 bg-gradient-to-b from-neutral-50 to-neutral-400 bg-clip-text text-4xl font-bold text-transparent md:text-5xl lg:text-6xl">
                <Motion let:motion custom={0} {variants} initial="hidden" animate={'visible'}>
                    <div use:motion>
                        {#each words.split(' ') as word, idx (`${word}${idx}`)}
                            <Motion let:motion {variants} custom={idx + 1} initial="hidden" animate={'visible'}>
                                <span use:motion class="text-black dark:text-white">
                                    {word}{' '}
                                </span>
                            </Motion>
                        {/each}
                    </div>
                </Motion>
            </div>
        </div>
    </div>