<script>
  import Header from "./Components/Header.svelte";
  import Footer from "./Components/Footer.svelte";
  import PollList from "./Components/PollList.svelte";
  import CreatePollForm from "./Components/CreatePollForm.svelte";
  import Tabs from "./Shared/Tabs.svelte";
  //tabs
  let items = ["Current Polls", "Add New Poll"];
  let activeItem = "Current Polls";
  const tabChange = (event) => {
    activeItem = event.detail;
  };

  const handleAdd = () => {
    activeItem = "Current Polls";
  };
</script>

<Header />
<main>
  <Tabs {activeItem} {items} on:tabChange={tabChange} />
  {#if activeItem === "Current Polls"}
    <PollList />
  {:else if activeItem === "Add New Poll"}
    <CreatePollForm on:add={handleAdd} />
  {/if}
</main>
<Footer />

<style>
  main {
    max-width: 960px;
    margin: 0 auto 40px;
  }
</style>
