<script lang="ts">
    import Input from "$lib/components/ui/Input/Input.svelte";
  import { onMount } from "svelte";

    interface RadixItem {
        base: number;
        regExp: RegExp;
        input?: HTMLInputElement;
    }

    let radixes: RadixItem[] = $state([
        { base:  2, regExp: /[^0-1]/g },
        { base:  8, regExp: /[^0-7]/g },
        { base: 10, regExp: /[^0-9]/g },
        { base: 16, regExp: /[^0-9a-fA-F]/g }
    ])

    onMount(() => {
        const inputs = Array.from(document.querySelectorAll(".radix-conversion-input"));

        radixes.forEach((radixItem, index) => radixItem.input = inputs[index] as HTMLInputElement);
    });

    const oninput = (e: Event) => {
        const currentRadixItem = radixes.find((radixItem) => radixItem.input === e.target);
        if ((!currentRadixItem) || (!currentRadixItem.input)) { return; }

        currentRadixItem.input.value = currentRadixItem.input.value.replace(currentRadixItem.regExp, ''); // 入力値のバリデーション

        let value = currentRadixItem.input.value;
        value = (value.endsWith('.')) ? `${value}0` : value;

        const decValue = parseInt(value, currentRadixItem.base);
        console.log(decValue);
        if (isNaN(decValue)) {
            radixes.forEach((radixItem) => radixItem.input!.value = "");
            return;
        }

        for (const radixItem of radixes) {
            if (!radixItem.input) { continue; }

            radixItem.input.value = decValue.toString(radixItem.base).toUpperCase();
        }
    };
</script>
<div class="min-h-screen flex flex-col justify-center items-center gap-3">
    {#each radixes as radixItem}
        <!-- TODO:画面幅に合わせるようにする(なんか効かない) -->
        <Input {oninput} placeholder={`${radixItem.base}進数`} type="text" class="radix-conversion-input w-50" />
    {/each}
</div>
