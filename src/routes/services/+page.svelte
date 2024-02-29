<script>
// @ts-nocheck

    import Sparkles from "$lib/components/ui/Sparkles/Sparkles.svelte";
	import CardBody from "$lib/components/ui/ThreeDCardEffect/CardBody.svelte";
	import CardContainer from "$lib/components/ui/ThreeDCardEffect/CardContainer.svelte";
	import CardItem from "$lib/components/ui/ThreeDCardEffect/CardItem.svelte";
	import Button from "$lib/components/ui/button/button.svelte";
	import { fade, slide, scale } from 'svelte/transition';
	import { onMount } from "svelte";
	import ContainerScrollAnimation from "$lib/components/ui/ContainerScrollAnimation/ContainerScrollAnimation.svelte";

	let isMouseEntered = false;

	const services = [
		{
			title: 'Full Product Delivery',
			description: '100% Done-For-You from idea to MVP. Including design, branding, AI-Features implementation, Prototype Strategy and more.',
			url: '/services/fpd',
			cta: 'Learn more about this',
			pros: ["Faster Time-To-Market", "Reduced Cost", "Reduced Risk"],
			image: '',
			active: true,
		},
		{
			title: 'Web Development',
			description: '100% Done-For-You from idea to MVP. Including design, branding, AI-Features implementation, Prototype Strategy and more.',
			url: '/services/webdev',
			cta: 'Learn more about this',
			pros: ["Faster Time-To-Market", "Reduced Cost", "Reduced Risk"],
			image: '',
			active: true,
		},
		{
			title: 'UI/UX Design',
			description: '100% Done-For-You from idea to MVP. Including design, branding, AI-Features implementation, Prototype Strategy and more.',
			url: '/services/design',
			cta: 'Learn more about this',
			pros: ["Faster Time-To-Market", "Reduced Cost", "Reduced Risk"],
			image: '',
			active: true,
		},
		{
			title: 'AI',
			description: '100% Done-For-You from idea to MVP. Including design, branding, AI-Features implementation, Prototype Strategy and more.',
			url: '/services/ai',
			cta: 'Learn more about this',
			pros: ["Faster Time-To-Market", "Reduced Cost", "Reduced Risk"],
			image: '',
			active: true,
		},
	]

	let showTitle;
	$: showTitle = false;

	onMount(() => {
		showTitle = true;
	})


	export const users = [
  {
    name: "Full Product Delivery",
    designation: "Testable MVP",
	url: "/services/fpd",
    image: "/bw.jpg",
    badge: "Full Product Delivery",
  },
  {
    name: "Web Development",
    designation: "Professional Online Presence",
	url: "/services/webdev",
    image: "/speaker.jpg",
    badge: "Web Development"
  },
  {
    name: "UI/UX",
    designation: "Graphic Design & Brand Strategy",
	url: "/services/design",
    image: "/3ddesign.jpg",
	badge: "UI/UX Design"
  },
  {
    name: "AI",
    designation: "Custom AI Chatbot",
	url: "/services/ai",
    image: "/AIgirl.jpg",
    badge: "AI"
  },
  {
    name: "Web Development",
    designation: "High-Converting Landing Page",
	url: "/services/webdev",
    image: "/landn.jpg",
    badge: "Web Development"
  },
  {
    name: "AI",
    designation: "ML-Based Analytics",
	url: "/services/ai",
    image: "/analysis.jpg",
    badge: "AI"
  },
  {
    name: "Full Product Delivery",
    designation: "Low-Risk Idea Validation",
	url: "/services/fpd",
    image: "/start.jpg",
    badge: "Full Product Delivery"
  },
  {
    name: "UI/UX",
    designation: "Figma Mockups",
	url: "/services/design",
    image: "/figma.jpg",
    badge: "UI/UX Design"
  },
  {
    name: "Web Development",
    designation: "User Stories",
	url: "/services/webdev",
    image: "/stori.jpg",
    badge: "Web Development"
  },
  {
    name: "Full Product Delivery",
    designation: "Reduced Idea Validation Costs",
	url: "/services/fpd",
    image: "/valid.jpg",
    badge: "Full Product Delivery"
  },
  {
    name: "UI/UX Design",
    designation: "Logo Design",
	url: "/services/design",
    image: "/gd.jpg",
    badge: "Graphic Design"
  },
  {
    name: "Web Development",
    designation: "Your Custom Solution",
	url: "/services/custom",
    image: "/custom.jpg",
    badge: "Custom"
  },

];


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
</script>



<div class="flex-col overflow-hidden hidden md:flex mt-20">
	<ContainerScrollAnimation {users}>
		<h1 slot="titleComponent" class="text-4xl font-semibold text-black dark:text-white">
			<span class="font-bold opacity-30">
				What we love, what we do,
			</span>
			<br>
			<span class="mt-1 text-4xl font-bold leading-none md:text-[6rem]"> Our Offer to You</span>
		</h1>
	</ContainerScrollAnimation>
	<div class="w-full h-full px-4 flex flex-row gap-2 justify-center items-center mb-10">
		{#each actionButtons as s}
			<Button href={s.url} class="">
				{s.title}
			</Button>
		{/each}
	</div>
</div>

<div class="w-full h-full flex flex-col px-6 min-h-[80vh] justify-center items-start md:hidden">
	<h1 class="text-4xl font-semibold text-black dark:text-white">
		<span class="font-bold opacity-30 text-2xl">
			What we love, what we do,
		</span>
		<br>
		<span class="mt-1 text-5xl font-bold leading-none md:text-[6rem]"> Our Offer to You</span>
	</h1>

	<div class="w-full h-full py-10 flex flex-row gap-2 justify-start flex-wrap items-center mb-10">
		{#each actionButtons as s}
			<Button href={s.url} class="">
				{s.title}
			</Button>
		{/each}
	</div>

</div>