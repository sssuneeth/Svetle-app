<script lang="ts">
  let name: string;
  let role: string;
  let age: number;
  let stack: string[] = [];

  const handleFormSubmit = () => {
    console.log(name, role, age, stack);
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
      <!-- <input
        type="text"
        placeholder="Role"
        class="w-full outline-none p-2 pl-3 bg-transparent border text-sm"
        bind:value={role}
      /> -->
      <select
        bind:value={role}
        class="w-full outline-none p-2 pl-3 bg-transparent border text-sm"
      >
        <option value="fullstack">Full stack</option>
        <option value="frontend">Frontend</option>
        <option value="backend">Backend</option>
      </select>
    </div>
    <div>
      <input
        type="number"
        placeholder="Age"
        class="w-full outline-none p-2 pl-3 bg-transparent border border-t-0 rounded-b text-sm"
        bind:value={age}
      />
    </div>
    <div class="text-start mt-2">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label class="text-sm font-semibold">Stack:</label> <br />
      <input type="checkbox" bind:group={stack} value="django" />
      <span class="text-sm">Django</span> <br />
      <input type="checkbox" bind:group={stack} value="svelte" />
      <span class="text-sm">Svelte</span> <br />
      <input type="checkbox" bind:group={stack} value="react" />
      <span class="text-sm">React</span>
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
