<script lang="ts">
  import { slide } from 'svelte/transition';
  import { spring } from 'svelte/motion';

  const width = spring(500, {
    damping: 0.25,
    stiffness: 0.075
  });

  let tab = 0;
</script>


<main class="my-8 space-y-8">
  <section class="mx-4 space-y-6">
    <div class="space-y-2">
      <div class="space-y-1">
        <p>Stiffness: {width.stiffness}</p>
        <p class="text-xs text-gray-500">Controls how fast the animation must go. Higher values makes the animation quickly bounce back and forth.</p>
      </div>
      <input class="w-full" type="range" min="0" max="1" step="0.01" bind:value={width.stiffness}>
    </div>
    <div class="space-y-2">
      <div class="space-y-1">
        <p>Damping: {width.damping} </p>
        <p class="text-xs text-gray-500">Controls the friction that tries to stop the animation. Lower values increase the distance the animation travels.</p>
      </div>
      <input class="w-full" type="range" min="0" max="1" step="0.01" bind:value={width.damping}>
    </div>
    <div class="space-y-3">
      <button class="px-4 py-2 self-start bg-gray-200 hover:bg-gray-100" on:click={() => width.update((targetVal) => targetVal === 150 ? 500 : 150)}>Change bar width</button>
      <div class="h-8 bg-indigo-700 rounded-lg text-center leading-8 text-white" style="width: {$width}px">{Math.round($width)}px</div>
    </div>
  </section>
  <section class="mx-4 space-y-2">
    <p>tab {tab}</p>
    <div class="p-4 bg-indigo-50 rounded-lg flex space-x-2">
      <button class="flex-1 p-4 bg-indigo-700 hover:bg-indigo-600 rounded-lg text-white focus:outline-none focus:ring-2" on:click={() => (tab = 1)}>Tab 1</button>
      <button class="flex-1 p-4 bg-indigo-700 hover:bg-indigo-600 rounded-lg text-white focus:outline-none focus:ring-2" on:click={() => (tab = 2)}>Tab 2</button>
      <button class="flex-1 p-4 bg-indigo-700 hover:bg-indigo-600 rounded-lg text-white focus:outline-none focus:ring-2" on:click={() => (tab = 3)}>Tab 3</button>
      <button class="flex-1 p-4 bg-indigo-700 hover:bg-indigo-600 rounded-lg text-white focus:outline-none focus:ring-2" on:click={() => (tab = 4)}>Tab 4</button>
    </div>
    <div>

      {#if tab === 1}
        <article
          class="p-4 bg-indigo-50 rounded-lg"
          in:slide={{ duration: 500, delay: 300 }}
          out:slide={{ duration: 300 }}
        >
          Repellat ut vitae et minima cumque veniam. Ut dolore voluptates corrupti.
          Repellendus enim consequuntur corrupti. Architecto esse labore rem rerum
          error nisi eaque. Aut aliquid a odio facilis est tenetur. Odit qui
          dolores. Corrupti porro fuga molestiae ut natus maiores quia quia. Non eum
          aspernatur vel. Consequatur ducimus placeat libero voluptatum ipsam
          aspernatur voluptate dignissimos.
        </article>
      {/if}
      {#if tab === 2}
        <article
          class="p-4 bg-indigo-50 rounded-lg"
          in:slide={{ duration: 500, delay: 300 }}
          out:slide={{ duration: 300 }}
        >
          Repellat ut vitae et minima cumque veniam. Ut dolore voluptates corrupti.
          Repellendus enim consequuntur corrupti. Architecto esse labore rem rerum
          error nisi eaque. Aut aliquid a odio facilis est tenetur. Odit qui
          dolores. Corrupti porro fuga molestiae ut natus maiores quia quia. Non eum
          aspernatur vel. Consequatur ducimus placeat libero voluptatum ipsam
          aspernatur voluptate dignissimos.
        </article>
      {/if}
      {#if tab === 3}
        <article
          class="p-4 bg-indigo-50 rounded-lg"
          in:slide={{ duration: 500, delay: 300 }}
          out:slide={{ duration: 300 }}
        >
          Repellat ut vitae et minima cumque veniam. Ut dolore voluptates corrupti.
          Repellendus enim consequuntur corrupti. Architecto esse labore rem rerum
          error nisi eaque. Aut aliquid a odio facilis est tenetur. Odit qui
          dolores. Corrupti porro fuga molestiae ut natus maiores quia quia. Non eum
          aspernatur vel. Consequatur ducimus placeat libero voluptatum ipsam
          aspernatur voluptate dignissimos.
        </article>
      {/if}
      {#if tab === 4}
        <article
          class="p-4 bg-indigo-50 rounded-lg"
          in:slide={{ duration: 500, delay: 300 }}
          out:slide={{ duration: 300 }}
        >
          Repellat ut vitae et minima cumque veniam. Ut dolore voluptates corrupti.
          Repellendus enim consequuntur corrupti. Architecto esse labore rem rerum
          error nisi eaque. Aut aliquid a odio facilis est tenetur. Odit qui
          dolores. Corrupti porro fuga molestiae ut natus maiores quia quia. Non eum
          aspernatur vel. Consequatur ducimus placeat libero voluptatum ipsam
          aspernatur voluptate dignissimos.
        </article>
      {/if}
    </div>
  </section>
</main>
