<script lang="ts">
// @ts-nocheck

    import { useTransform, Motion, useViewportScroll } from "svelte-motion";
    import { onMount } from "svelte";
    export let users;
    let containerRef;
    let { scrollYProgress } = useViewportScroll();
    let isMobile = false;
    onMount(() => {
      const checkMobile = () => {
        isMobile = window.innerWidth <= 768;
      };
      checkMobile();
      window.addEventListener("resize", checkMobile);
      return () => {
        window.removeEventListener("resize", checkMobile);
      };
    });
    const scaleDimensions = () => {
      return isMobile ? [0.7, 0.9] : [1.05, 1];
    };
    $:
      rotate = useTransform(scrollYProgress, [0, 1], [20, 0]);
    $:
      scale = useTransform(scrollYProgress, [0, 1], scaleDimensions());
    $:
      translate = useTransform(scrollYProgress, [0, 1], [0, -100]);
    </script>
    
    <div class="relative flex items-center justify-center px-16" bind:this={containerRef}>
        <div class="relative w-full py-10" style="perspective: 800px;">
            <Motion
                let:motion
                style={{
                    translateY: translate
                }}
            >
                <div use:motion class="div mx-auto max-w-5xl text-center">
                    <slot name="titleComponent" />
                </div>
            </Motion>
            <Motion
                let:motion
                style={{
                    rotateX: rotate, // rotate in X-axis
                    scale,
                    boxShadow:
                        '0 0 #0000004d, 0 9px 20px #0000004a, 0 37px 37px #00000042, 0 84px 50px #00000026, 0 149px 60px #0000000a, 0 233px 65px #00000003'
                }}
            >
                <div
                    use:motion
                    class="mx-auto -mt-12 bg-black  h-[30rem] overflow-auto w-full max-w-5xl rounded-[30px] border-4 border-[#6C6C6C]  p-6 shadow-2xl md:h-[40rem]"
                >
                <!-- original bg-[#222222] -->
                    <div
                        class="grid h-full w-full grid-cols-1 gap-4 overflow-auto rounded-2xl bg-[#191919] p-4 md:grid-cols-3 lg:grid-cols-4"
                    >
                        {#each users as user, idx (`user-${idx}`)}
                            <Motion
                                let:motion
                                style={{ translateY: translate }}
                                whileHover={{
                                    boxShadow: '0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1)'
                                }}
                            >
                                <a href={user.url} use:motion class="relative text-white hover:text-black cursor-pointer rounded-xl border-[0.5px] border-white border-opacity-30 altashadow bg-black hover:bg-white transition-all ease-in-out duration-300">
                                    <div
                                        class="absolute right-2 top-2 rounded-full bg-black altashadow px-4 py-1 text-xs font-bold text-white z-50"
                                    >
                                        {user.badge}
                                    </div>
                                    <img src={user.image} class="rounded-tl-lg object-cover rounded-tr-lg w-60 h-52" alt="thumbnail" />
                                    <div class="w-60 h-52 bg-black bg-opacity-40 rounded-tl-xl rounded-tr-xl absolute top-0 z-30"/>
                                    <div class="p-4">
                                        <!-- <h1 class="text-sm font-semibold">{user.name}</h1> -->
                                        <h2 class=" text-md font-semibold  py-1">{user.designation}</h2>
                                    </div>
                                </a>
                            </Motion>
                        {/each}
                    </div>
                </div>
            </Motion>
        </div>
    </div>