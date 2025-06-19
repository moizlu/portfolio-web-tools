<script lang="ts">
    import { page } from "$app/state";
    import LinkButton from "$lib/components/ui/LinkButton/LinkButton.svelte";
    import Icon from "$lib/components/ui/Icon/Icon.svelte";
</script>

<div class="flex flex-col justify-center items-center">
    <h1>{page.status}</h1>
    <h1>{page.error?.message}</h1>
    <LinkButton href="/" class="flex justify-center items-center my-5 p-2">
        <Icon lightSrc="/icons/light/home.svg" darkSrc="/icons/dark/home.svg" width={30} class="drop-shadow-primary drop-shadow-sm m-2" />
        <p class="text-sm md:text-xl">ホームに戻る</p>
    </LinkButton>
</div>
