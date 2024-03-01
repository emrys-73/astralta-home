<script>
	import '../app.pcss';
	import Sun from "svelte-radix/Sun.svelte";
  	import Moon from "svelte-radix/Moon.svelte";
	import { Button } from "$lib/components/ui/button";
	import { ModeWatcher } from 'mode-watcher';
	import { setMode } from 'mode-watcher';
	import * as Menubar from "$lib/components/ui/menubar";
 
  	import { toggleMode } from "mode-watcher";
	import { onMount } from 'svelte';

	onMount(() => {
		setMode('dark')
	})

	const menu = [
		{
			title: "Services",
			url: '/services',
			active: true,
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
			title: "Contact",
			url: 'mailto:montoya@astralta.com',
			active: true,
		},

	]

	const menuSmall = [
		{
			title: "Full Product Delivery",
			url: '/services/fpd',
			active: true,
		},
		{
			title: "Web Development",
			url: '/services/webdev',
			active: true,
		},
		{
			title: "UI/UX Design",
			url: '/services/design',
			active: true,
		},
		{
			title: "AI x Astralta",
			url: '/services/ai',
			active: true,
		},
		{
			title: "Contact",
			url: 'mailto:montoya@astralta.com',
			active: true,
		},
	]
	
</script>

<div class="relative min-h-screen">
	<div class="w-full h-16 relative py-4 top-0 px-4 justify-center items-center flex flex-col bg-transparent">
		<div class="w-4/5 lg:w-3/4 h-12 flex flex-row justify-between items-center rounded-full dark:bg-white bg-black bg-opacity-5 z-50 dark:bg-opacity-10 backdrop-blur-md fixed top-4 border-2 border-opacity-0 border-white px-6">
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

	<div class="absolute bottom-0 flex w-full h-12 bg-white bg-opacity-5 text-white text-xs justify-center items-center">
		<span class="w-full h-full opacity-50 text-center justify-center items-center flex">
			Copyright © 2023 Astralta Inc. All rights reserved.
		</span>
	</div>
</div>


