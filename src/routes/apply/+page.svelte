<script>
	import { onMount } from "svelte";
    import { footerColor } from "../../stores";

    onMount( async () => {
        footerColor.set("bg-gradient-to-b from-[#0CBE66] to-black")
    })

</script>


<div>


</div>