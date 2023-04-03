<script>
  export let showModal = false;

  // once - it removes the refernce once we triggerd
  // preventDefault
  // self
</script>

{#if showModal}
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="modal-overlay absolute inset-0 bg-black/50 flex justify-center pt-20 z-10" on:click|self>
    <div class="modal bg-stone-50 h-max w-[350px] rounded-md px-5 py-7 shadow-lg">
      <slot />
    </div>
  </div>
{/if}
