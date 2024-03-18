<script>
// @ts-nocheck

	import { onMount } from "svelte";
    import { footerColor } from "../../stores";
    import * as Select from "$lib/components/ui/select";

    onMount( async () => {
        footerColor.set("bg-gradient-to-b from-[#0BA457] to-[#035020]")
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


<div class="w-full h-full min-h-screen px-6 md:px-10 lg:px-20 py-20 relative justify-center items-center">

    <div class="w-[300px] h-[300px] bg-[#0CBE66] blur-[200px] absolute -top-[280px] z-10"/>

    <div class="z-20 relative flex">
        <h1 class="md:text-7xl text-5xl font-bold uppercase">
            Start here
        </h1>
    </div>

    <div>
        <p class="text-white py-4 opacity-70">
            Fields marked with * are mandatory
        </p>
    </div>


    <form action="https://submit-form.com/vMMtwUHYY" class="flex flex-col  gap-6 py-20 z-20 relative w-full justify-center items-center">
        <!-- <input
            type="hidden"
            name="_redirect"
            value="/apply/success"
        />

        <input type="hidden" name="_error" value="/apply/error" /> -->
        
        <div class="w-full py-4 flex flex-col gap-2">
            <label for="name" class="px-6">* Name</label>
            <input type="text" id="name" name="name" placeholder="Your name" required="true" class="bg-white bg-opacity-10 rounded-full text-white placeholder:text-white placeholder:text-opacity-50 px-4 py-2 w-full" />
        </div>

        <div class="w-full py-4 flex flex-col gap-2">
            <label for="email" class="px-6">* EMail</label>
            <input type="text" id="email" name="email" placeholder="Your E-Mail" required="true" class="bg-white bg-opacity-10 rounded-full text-white placeholder:text-white placeholder:text-opacity-50 px-4 py-2" />
        </div>
        
        <div class="w-full py-4 flex flex-col gap-2">
            <label for="socials" class="px-6">Business website and socials</label>
            <input type="text" id="socials" name="socials" placeholder="Send us any existing website for your business and any relevant socials you wish to share with us." required="" class="bg-white bg-opacity-10 rounded-full text-white placeholder:text-white placeholder:text-opacity-50 px-4 py-2" />
        </div>

        <div class="w-full py-4 flex flex-col gap-2">
            <label for="business_description" class="px-6">* Business description</label>
            <input type="text" id="business_description" name="business_description" placeholder="Tell us about your business. i.e. what do you sell, how do you sell it and for how much?" required="" class="bg-white bg-opacity-10 rounded-full text-white placeholder:text-white placeholder:text-opacity-50 px-4 py-2" />
        </div>

        <div class="w-full py-4 flex flex-col gap-2">
            <label for="funnel" class="px-6">How did you find us?</label>
            <Select.Root class="w-full ">
                <Select.Trigger class="w-full bg-white bg-opacity-10 rounded-full px-4">
                  <Select.Value placeholder="Choose one" />
                </Select.Trigger>
                <Select.Content>
                  <Select.Group>
                    <Select.Label>Choose one</Select.Label>
                    {#each funnels as fun}
                      <Select.Item value={fun.value} label={fun.label}
                        >{fun.label}</Select.Item
                      >
                    {/each}
                  </Select.Group>
                </Select.Content>
                <Select.Input name="funnel" />
              </Select.Root>
        </div>

        <div class="w-full py-4 flex flex-col gap-2">
            <label for="services" class="px-6">What are you looking for?</label>
            <Select.Root class="w-full ">
                <Select.Trigger class="w-full bg-white bg-opacity-10 rounded-full px-4">
                  <Select.Value placeholder="Choose a service" />
                </Select.Trigger>
                <Select.Content>
                  <Select.Group>
                    <Select.Label>Choose a service</Select.Label>
                    {#each services as s}
                      <Select.Item value={s.value} label={s.label}
                        >{s.label}</Select.Item
                      >
                    {/each}
                  </Select.Group>
                </Select.Content>
                <Select.Input name="funnel" />
              </Select.Root>
        </div>

        <div class="w-full py-4 flex flex-col gap-2">
            <label for="problem" class="px-6">* What's hurting?</label>
            <input type="textarea" id="problem" name="problem" placeholder="What is the problem you are trying to solve with our services?" required="true" class="bg-white bg-opacity-10 rounded-full text-white placeholder:text-white placeholder:text-opacity-50 px-4 py-2" />
        </div>

        <div class="w-full py-4 flex flex-col gap-2">
            <label for="solution" class="px-6">* How can we help?</label>
            <input type="text" id="solution" name="solution" placeholder="What's the dream outcome we can provide you?" required="true" class="bg-white bg-opacity-10 rounded-full text-white placeholder:text-white placeholder:text-opacity-50 px-4 py-2" />
        </div>


        <button type="submit" class="bg-[#0BA457] text-white font-semibold text-3xl rounded-full mt-20 py-1 w-3/4 hover:w-full transition-all duration-300 ease-in-out">
            Send application
        </button>

      </form>

</div>