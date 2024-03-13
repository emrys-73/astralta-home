<script>
	import '../app.pcss';
	import Sun from "svelte-radix/Sun.svelte";
  	import Moon from "svelte-radix/Moon.svelte";
	import { Button } from "$lib/components/ui/button";
	import InfiniteMovingFooter from '$lib/components/ui/InfiniteMovingCards/InfiniteMovingFooter.svelte';
	import { ModeWatcher } from 'mode-watcher';
	import { setMode } from 'mode-watcher';
	import Circle from '$lib/components/ui/shapes/Circle.svelte';
	
	import * as Menubar from "$lib/components/ui/menubar";
 
  	import { toggleMode } from "mode-watcher";
	import { onMount } from 'svelte';

	onMount(() => {
		setMode('dark')
	})

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

	const menu = [
		{
			title: "Projects",
			url: '/projects',
			active: false,
		},
		{
			title: "Showcases",
			url: '/',
			active: false,
		},
		{
			title: "Pricing",
			url: '/pricing',
			active: false,
		},
		{
			title: "About",
			url: '/',
			active: false,
		},
		{
			title: "Get in Touch",
			url: 'mailto:montoya@astralta.com',
			active: true,
		},

	]

	const menuSmall = [
		{
			title: "Projects",
			url: '/projects',
			active: false,
		},
		{
			title: "Pricing",
			url: '/pricing',
			active: false,
		},
		{
			title: "Get in Touch",
			url: 'mailto:montoya@astralta.com',
			active: true,
		},
	]
	
</script>

<div class="relative min-h-screen flex flex-col">
	<div class="w-full h-16 relative py-4 top-0 px-4 justify-center items-center flex flex-col bg-transparent">
		<div class="w-4/5 lg:w-3/4 h-12 flex flex-row justify-between items-center rounded-full dark:bg-[#656565] bg-black bg-opacity-5 z-50 dark:bg-opacity-10 backdrop-blur-md fixed top-4 border-2 border-opacity-0 border-white px-6">
			<a href="/" class="flex flex-row justify-center items-center">
	
				<img src="/logo_white.png" alt="logo" class="w-6 mx-2 hidden dark:flex hover:w-7 transition-all ease-in-out duration-300">
				<img src="/logo_dark.png" alt="logo" class="w-6 mx-2 dark:hidden flex">
	
				<div class="">
					
				</div>
			</a>
	
			<div class="w-full h-full flex-row hidden md:flex justify-end px-2 gap-8 text-sm items-center">
				{#each menu as m}
					{#if m.active}
						<a href={m.url} class="hover:text-[#FFF] text-[#FFF] transition-all duration-500 ease-in-out opacity-80 hover:opacity-100">
							{m.title}
						</a>
					{/if}
				{/each}
			</div>
	
			<div class="md:hidden flex">
				<Menubar.Root class="bg-transparent">
					<Menubar.Menu>
					  <Menubar.Trigger>
						<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
							<path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
						  </svg>					  
					  </Menubar.Trigger>
					  <Menubar.Content class="bg-transparent backdrop-blur-lg">
						{#each menuSmall as m}
							{#if m.active}
								<a href={m.url} class="hover:cursor-pointer">
									<Menubar.Item class="hover:cursor-pointer">
										{m.title}
									</Menubar.Item>
								</a>
							{/if}
						
						{/each}
					  </Menubar.Content>
					</Menubar.Menu>
				  </Menubar.Root>
			</div>
		</div>
	</div>
	
	<ModeWatcher/>
	
	<div>
		<slot />
	</div>

	<div class="flex w-full min-h-[80vh] bg-gradient-to-b py-20 from-[#6939F1] to-black text-white text-xs justify-end items-center relative flex-col overflow-hidden ">
		<div class="absolute -bottom-[40vh] w-[60vw] h-[100vh] flex bg-black rounded-full blur-[200px] z-10"/>

		<div class="text-white w-1/2 z-20">
			<ul class="flex flex-col gap-2">
				<!-- <li>
					<a href="/#work" class="hover:opacity-100 opacity-70 text-2xl hover:text-3xl transition-all duration-300 ease-in-out">
						<h3 class="font-semibold">
							Projects
						</h3>
					</a>
				</li>
				<li>
					<a href="/pricing" class="hover:opacity-100 opacity-70 text-2xl hover:text-3xl transition-all duration-300 ease-in-out w-full">
						<h3 class="font-semibold">
							Pricing
						</h3>
					</a>
				</li> -->
				<li>
					<a href="mailto:montoya@astralta.com" class="hover:opacity-100 opacity-70 text-2xl hover:text-3xl transition-all duration-300 ease-in-out">
						<h3 class="font-semibold">
							Get in touch
						</h3>
					</a>
				</li>
			</ul>
		</div>

		<div class="pt-20">
			<InfiniteMovingFooter items={testimonials} direction="right" speed="slow"/>
		</div>
		<span class="w-full h-12 opacity-50 text-center justify-between px-6 md:px-10 lg:px-20 items-center flex absolute bottom-4 flex-col md:flex-row gap-4">
			<span>
				Designed in Munich, Germany
			</span>
			<span>
				Copyright © 2023 Astralta Inc. All rights reserved.
			</span>
		</span>
	</div>
</div>


