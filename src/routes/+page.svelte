<script>
  import Layout from "./+layout.svelte";

  let color = "Black";
  let firstName = "John";
  let lastName = "Doe";
  // reactive for getting fullName
  $: fullName = `${firstName} ${lastName}`;
</script>

<main>
  <div class="w-screen h-screen flex items-center flex-col pt-48">
    <h2 class="text-xl">{fullName} - {color} belt</h2>
    <div>
      <input
        type="text"
        class="border-2 pl-3 p-1 mt-2 outline-none"
        bind:value={firstName}
      />
      <input
        type="text"
        class="border-2 pl-3 p-1 mt-2 outline-none"
        bind:value={lastName}
      />
      <input
        type="text"
        class="border-2 pl-3 p-1 mt-2 outline-none"
        bind:value={color}
      />
    </div>
  </div>
</main>
