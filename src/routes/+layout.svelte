<script lang="ts">
    import { fly } from 'svelte/transition'
    import PageTransition from '$lib/transition.svelte'
    export let data
</script>

{#key data.url}
    <div
            in:fly={{ x: -200, duration: 300, delay: 300 }}
            out:fly={{ x: 200, duration: 300 }}>
        <PageTransition key={data.url} duration={2000}>
        <slot />
            </PageTransition>
    </div>
{/key}