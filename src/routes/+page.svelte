<script lang="ts">
    import LinkButton from "$lib/components/ui/LinkButton/LinkButton.svelte";
    import Icon from "$lib/components/ui/Icon/Icon.svelte";
</script>

{#snippet drawLink(href: string, lightSrc: string, darkSrc: string, alt: string, name: string)}
    <LinkButton {href} class="flex justify-center items-center p-2">
        <Icon {lightSrc} {darkSrc} {alt} class="drop-shadow-primary drop-shadow-sm" />
        <p>{name}</p>
    </LinkButton>
{/snippet}

<div class="flex flex-col justify-center items-center gap-5">
    <h1>ツール集</h1>

    {@render drawLink("/radix-conversion", "/icons/light/conversion.svg", "/icons/dark/conversion.svg", "conversion", "基数変換")}
</div>