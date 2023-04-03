<script lang="ts">
  import { createEventDispatcher } from "svelte";
  
  let dispatch = createEventDispatcher();

  let name: string;
  let role: string;
  let age: number;

  const handleFormSubmit = () => {
    // create person object
    const person = {
      name,
      role,
      age,
      id: Math.random()
    }
    dispatch('addPerson', person)
  };
</script>

<div class="text-center">
  <h4 class="mb-2 font-semibold text-lg">Add person</h4>
  <form on:submit={handleFormSubmit}>
    <div>
      <input
        type="text"
        placeholder="Name"
        class="w-full outline-none p-2 pl-3 bg-transparent border border-b-0 rounded-t text-sm"
        bind:value={name}
      />
    </div>
    <div>
      <input
        type="text"
        placeholder="Role"
        class="w-full outline-none p-2 pl-3 bg-transparent border text-sm"
        bind:value={role}
      />
    </div>
    <div>
      <input
        type="number"
        placeholder="Age"
        class="w-full outline-none p-2 pl-3 bg-transparent border border-t-0 rounded-b text-sm"
        bind:value={age}
      />
    </div>
    <div>
      <button
        class="bg-stone-700 text-white p-2 px-5 text-xs w-full mt-3 font-semibold rounded"
        >Submit</button
      >
    </div>
  </form>
</div>

<style>
</style>
