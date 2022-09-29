<script>
  import Header from "./Components/Header.svelte";
  import Footer from "./Components/Footer.svelte";
  import Tabs from "./Shared/Tabs.svelte";
  //tabs
  let items = ["Current Polls", "Add New Poll"];
  let activeItem = "Current Polls";
  const tabChange = (e) => {
    activeItem = e.detail;
  };
</script>

<Header />
<main>
  <Tabs {activeItem} {items} on:tabChange={tabChange} />
  {#if activeItem === "Current Polls"}
    <p>Poll list component goes here</p>
  {:else if activeItem === "Add New Poll"}
    <p>New poll component goes here</p>
  {/if}
</main>
<Footer />

<style>
  main {
    max-width: 960px;
    margin: 0 auto 40px;
  }
</style>
