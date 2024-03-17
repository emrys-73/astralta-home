<script>
	import { onMount } from "svelte";
    import { footerColor } from "../../../stores";

    onMount( async () => {
        footerColor.set("bg-gradient-to-b from-[#FF620B] to-[#000000]")
    })

</script>


<div>
    <div>
        <h1>
            PFOLIO
        </h1>
    </div>

</div>