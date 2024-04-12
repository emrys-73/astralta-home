<script>
// @ts-nocheck

	import { onMount } from "svelte";
    import { footerColor } from "../../stores";
    import * as Select from "$lib/components/ui/select";

    onMount( async () => {
        footerColor.set("bg-gradient-to-b from-[#0BA457] to-[#035020]")
        const script = document.createElement('script');
      script.src = 'https://tally.so/widgets/embed.js';
      script.async = true;
      document.head.appendChild(script);
    })

    const funnels = [
    { value: "Social Media", label: "Social Media" },
    { value: "Referral", label: "Referral" },
    { value: "Revelation in a dream", label: "Revelation in a dream" },
    { value: "Other", label: "Other" },
  ];

  const services = [
    { value: "Website", label: "Website" },
    { value: "Web App MVP", label: "Web App MVP" },
    { value: "UI/UX Design", label: "UI/UX Design" },
    { value: "Other", label: "Other" },
  ];

</script>


<div class="w-full h-full min-h-screen">
  <iframe data-tally-src="https://tally.so/r/wzqVdk?transparentBackground=1" frameborder="0" marginheight="0" marginwidth="0" title="Apply for a free strategy call" class="w-full h-full min-h-screen"></iframe>
</div>