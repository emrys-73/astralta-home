<script lang="ts">
//@ts-nocheck

    import { cn } from "$lib/utils";
    export let className;
    </script>
    
    <div
        class={cn(
            'h-96 w-96 [transform-style:preserve-3d]  [&>*]:[transform-style:preserve-3d]',
            className
        )}
    >
        <slot />
    </div>