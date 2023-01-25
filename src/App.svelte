<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./components/Tabs.svelte";
  import CreateForm from "./components/CreateForm.svelte";
  import About from "./components/About.svelte";
  const items = ["Live Polls", "Past Polls", "Create Poll", "About Me"];
  let active = items[0];

  const tabChange = (e) => {
    active = e.detail;
  };
</script>

<main>
  <Header/>
  <main class="min-h-screen">
    <Tabs {items} {active} on:change={tabChange} />
    <!-- <CreateForm/> -->
    <!-- <About/> -->
  </main>
  <Footer/>
</main>
