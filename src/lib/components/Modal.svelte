<script>
  export let title = 'Default title';
  export let showModal = false;
</script>

{#if showModal}
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="modal-overlay absolute inset-0 bg-black/50 flex justify-center pt-32 z-10" on:click>
    <div class="modal bg-stone-50 h-max w-[500px] rounded-md px-5 py-7 shadow-lg">
      <h3
        class="text-xl font-semibold text-center"
      >
        {title}
      </h3>
    </div>
  </div>
{/if}
