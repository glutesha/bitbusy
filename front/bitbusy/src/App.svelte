<script lang="ts">
  import Busy from './lib/Busy.svelte'
  import Pause from './lib/Pause.svelte'
  import Clock from './lib/Clock.svelte';
  import String from './lib/String.svelte';
  import { load } from './main';
  import { onMount } from 'svelte';
  import Select from './lib/Select.svelte';
  import { select } from './select';
    import Send from './lib/Send.svelte';
    import Color from './lib/Color.svelte';

  onMount(load);
</script>

<main class="bg-neutral-900">
  <div class="flex flex-col h-screen items-center justify-center gap-5">
    <div class="flex flex-col items-center justify-center gap-1">
      <p class="text-7xl font-bold text-white">Bit::Busy</p>
      <div class="flex flex-row items-center gap-3">
        <img
          src="gluten.svg"
          alt="Glutesha logo"
          class="size-10"
        />
        <p class="text-2xl text-white">By Glutesha Devices</p>
      </div>
   </div>
      <div class="flex flex-col items-center gap-2">
        {#if $select == 3}
          <String />
          <Color />
        {/if}
        {#if $select == 1 || $select == 2}
          <Clock />
        {/if}
        <Select />
        {#if $select == 3}
          <Send />
        {/if}
        {#if $select != 3}
          <Busy />
        {/if}
        {#if $select == 1 || $select == 2}
          <Pause />
        {/if}
    </div>
  </div>
</main>
