<script>
  import Layout from "./+layout.svelte";

  let array = [
    { title: 'Learning svelte', id:1 },
    { title: 'Contributing opensource', id:2 },
    { title: 'Doing freelance jobs', id:3 }
  ];
</script>

<main>
  <div class="w-screen h-screen flex items-center flex-col pt-48">
    {#each array as item (item.id)}
      <h2 class="text-xl font-semibold underline underline-offset-8 decoration-stone-300 py-2">{item.id}. {item.title}</h2>
    {:else}
      <p>There is no items left in the array!</p>
    {/each}
  </div>
</main>