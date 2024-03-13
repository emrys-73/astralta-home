<script lang="ts">
	import { cn } from '$lib/utils';
	import { onMount } from 'svelte';

	export let items: {
		quote: string;
		name: string;
		title: string;
        content: string;
	}[];
	export let direction: 'left' | 'right' | undefined = 'left';
	export let speed: 'fast' | 'normal' | 'slow' | undefined = 'fast';
	export let pauseOnHover: boolean | undefined = true;
	export let className: string | undefined = undefined;

	let containerRef: HTMLDivElement;
	let scrollerRef: HTMLUListElement;

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
			if (direction === 'left') {
				containerRef.style.setProperty('--animation-direction', 'forwards');
			} else {
				containerRef.style.setProperty('--animation-direction', 'reverse');
			}
		}
	};
	const getSpeed = () => {
		if (containerRef) {
			if (speed === 'fast') {
				containerRef.style.setProperty('--animation-duration', '20s');
			} else if (speed === 'normal') {
				containerRef.style.setProperty('--animation-duration', '40s');
			} else {
				containerRef.style.setProperty('--animation-duration', '80s');
			}
		}
	};
</script>

<div
	bind:this={containerRef}
	class={cn(
		'scroller relative z-20 max-w-[95vw] overflow-hidden  [mask-image:linear-gradient(to_right,transparent,white_20%,white_80%,transparent)]',
		className
	)}
>
	<ul
		bind:this={scrollerRef}
		class={cn(
			' flex w-max min-w-full shrink-0 flex-nowrap gap-4',
			start && 'animate-scroll ',
			pauseOnHover && 'hover:[animation-play-state:paused]'
		)}
	>
		{#each items as item, idx (item.name)}
			<li
				class="relative flex-shrink-0"
			>
				<div>
                    <img src={item.content} alt="" class=" h-[200px] lg:h-[400px]">
                </div>
			</li>
		{/each}
	</ul>
</div>