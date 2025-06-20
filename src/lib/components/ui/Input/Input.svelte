<script lang="ts">
    import type { HTMLInputAttributes } from "svelte/elements";

    interface Props extends HTMLInputAttributes {}

    const { placeholder, class: className, ...props }: Props = $props();

    const id = crypto.randomUUID();

</script>

<div class="relative mt-3 w-full">
    <input {id} placeholder=" " class={[className, "peer p-2 border-1 border-accent"]} {...props} />
    <label for={id} class="absolute pointer-events-none left-3 -top-3 px-1
                           -z-1 peer-focus:z-1 not-peer-placeholder-shown:z-1
                           transition-transform duration-150
                           bg-primary
                           translate-y-5
                           peer-focus:translate-y-0
                           not-peer-placeholder-shown:translate-y-0
">{placeholder}</label>
</div>

