<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./components/Tabs.svelte";
  import CreateForm from "./components/CreateForm.svelte";
  import About from "./components/About.svelte";
  import PollsList from "./components/PollsList.svelte";
  const items = ["Live Polls", "Past Polls", "Create Poll", "About Me"];
  let active = items[0];

  const tabChange = (e) => {
    active = e.detail;
  };

  const pollCreated = (e) => {
    active = "Live Polls";
  };
</script>

<main>
  <Header/> 
  <main class="min-h-screen">
    <Tabs {items} {active} on:change={tabChange} />
    {#if active === "Live Polls"}
      <h1 class="text-3xl font-bold my-6">Live Polls</h1>
      <p class="text-slate-600 mb-4">
        This is where you can see all the live polls.
      </p>
      <PollsList/>
    {:else if active === "Past Polls"}
      <h1 class="text-3xl font-bold my-6">Past Polls</h1>
      <p class="text-slate-600 mb-4">
        This is where you can see all the past polls.
      </p>
      <PollsList/>
    {:else if active === "Create Poll"}
      <CreateForm on:pollCreated={pollCreated}/>
    {:else if active === "About Me"}
      <About/>
    {/if}
  </main>
  <Footer/>
</main>
