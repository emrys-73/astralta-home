<script lang="ts">
	import { Menubar as MenubarPrimitive } from "bits-ui";
	import { cn, flyAndScale } from "$lib/utils";

	type $$Props = MenubarPrimitive.ContentProps;
	let className: $$Props["class"] = undefined;
	export let align: $$Props["align"] = "start";
	export let alignOffset: $$Props["alignOffset"] = -4;
	export let sideOffset: $$Props["sideOffset"] = 8;
	export let transition: $$Props["transition"] = flyAndScale;
	export let transitionConfig: $$Props["transitionConfig"] = undefined;
	export { className as class };
</script>

<MenubarPrimitive.Content
	{transition}
	{transitionConfig}
	{sideOffset}
	{align}
	{alignOffset}
	class={cn(
		"z-50 min-w-[14rem] rounded-md border bg-popover p-1 text-popover-foreground drop-shadow-xl border-opacity-5 border-white focus:outline-none",
		className
	)}
	{...$$restProps}
>
	<slot />
</MenubarPrimitive.Content>
