<script lang="ts">
  import Layout from "./+layout.svelte";
  import Modal from "../lib/components/Modal.svelte";
  import AddPersonForm from '../lib/components/AddPersonForm.svelte';

  let people = [
    { name: "John Doe", age: 23, role: "fullstack", id: 1 },
    { name: "Suneeth", age: 36, role: "frontend", id: 2 },
    { name: "Foo man", age: 12, role: "backend", id: 3 },
  ];

  const handleRemovePerson = (id: Number) => {
    console.log(id);
    // remote person from array
    people = people.filter((person) => person.id !== id);
  };
  // show modal with boolean
  let showModal = false;
  // toggle modal
  const toggleModal = () => {
    showModal = !showModal;
  };
  // add person obj to array
  const handleAddPerson = (e: any) => {
    const person = e.detail;
    // add person to people array
    people = [person, ...people];
    showModal = false;
  }
</script>

<svelte:head>
  <title>Svetle-app</title>
</svelte:head>

<main>
  <div class="w-screen h-screen flex items-center flex-col pt-20">
    <div class="border p-7 rounded-md w-[350px]">
      <Modal {showModal} on:click={toggleModal}>
        <AddPersonForm on:addPerson={handleAddPerson} />
      </Modal>
      <div class="grid place-items-end">
        <button
          on:click={toggleModal}
          class="bg-stone-700 text-white p-2 px-5 text-xs font-semibold rounded"
        >
          Open modal
        </button>
      </div>
      {#each people as person (person.id)}
        <div class="py-3">
          <div class="flex items-center gap-3">
            <h2 class="text-xl font-semibold">
              {person.name}
            </h2>
            {#if person.age > 30}
              <span class="text-sm opacity-60">Senior devloper</span>
            {:else if person.age > 20}
              <span class="text-sm opacity-60">Junior devloper</span>
            {:else}
              <span class="text-sm opacity-60">Newbie</span>
            {/if}
          </div>
          <h4>{person.age} year old {person.role} developer.</h4>
          <button
            on:click={() => handleRemovePerson(person.id)}
            class="bg-stone-100 p-2 px-5 rounded mt-2 text-sm">Remove</button
          >
        </div>
      {:else}
        <p>There is no people left in the array!</p>
      {/each}
    </div>
  </div>
</main>
