<script lang="ts">
    import LinkButton from "$lib/components/ui/LinkButton/LinkButton.svelte";
</script>

<footer class="fixed bottom-0 left-0 flex justify-start items-center drop-shadow-primary drop-shadow-sm pointer-events-none">
    <img src="/logo/light/moizlu.svg" alt="logo" width={60} class="m-5 drop-shadow-black drop-shadow-sm">
    <div class="flex flex-col justify-center items-center">
        <p>もいずる</p>
        <p>moizlu</p>
    </div>

    <LinkButton href="https://moiz.lu/" isInvert={true} target="_blank" class="m-2 pointer-events-auto">
        <p class="m-2">リンク集</p>
    </LinkButton>
</footer>