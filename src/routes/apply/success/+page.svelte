<script>
    import Button from "$lib/components/ui/button/button.svelte";
    import { onMount } from "svelte";
    import { footerColor } from "../../../stores";
    import * as Select from "$lib/components/ui/select";

    onMount( async () => {
        footerColor.set("bg-gradient-to-b from-[#0BA457] to-[#035020]")
    })

</script>

<div class="w-full h-full min-h-[80vh] px-6 md:px-10 lg:px-20 py-20 relative justify-center items-center flex flex-col gap-6">

    <div class="w-[300px] h-[300px] bg-[#0BA457] blur-[200px] absolute -top-[280px] left-0 z-10"/>

    <div class="z-20 relative flex h-full w-full ">
        <h1 class="md:text-7xl text-5xl font-bold uppercase">
            You're in!
        </h1>
    </div>
    

    <div class="w-full ">
        <p>
            We will get back to you shortly once we review your application. Until then you can:
        </p>

        <div class="py-4">
            <Button href="mailto:montoya@astralta.com" class="hover:bg-[#0BA457] hover:text-white">
                Send us an E-Mail
            </Button>
            <Button href="/apply" class="bg-transparent text-white hover:text-[#0BA457] hover:bg-transparent">
                Go back home
            </Button>
        </div>

    </div>

    <div class="w-[600px] h-[600px] bg-[#0BA457] blur-[800px] opacity-50 absolute -bottom-[280px] -right-[200px] z-10"/>
</div>
    