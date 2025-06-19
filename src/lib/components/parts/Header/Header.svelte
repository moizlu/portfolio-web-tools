<script lang="ts">
    import Icon from "$lib/components/ui/Icon/Icon.svelte";
    import ThemeButton from "$lib/components/ui/ThemeButton/ThemeButton.svelte";
</script>

<header class="fixed top-0 left-0 w-full h-15 flex justify-between items-center pointer-events-none">
    <a href="/" class="flex pointer-events-auto">
        <Icon lightSrc="/icons/light/home.svg" darkSrc="/icons/dark/home.svg" alt="logo" width={40}  class="mx-5 drop-shadow-primary drop-shadow-sm" />
    </a>

    <ThemeButton class="pointer-events-auto" />
</header>
