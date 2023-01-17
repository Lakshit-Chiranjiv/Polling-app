<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./components/Tabs.svelte";
  const items = ["Live Polls", "Past Polls", "Create Poll", "About Me"];
  let active = items[0];
</script>

<main>
  <Header/>
  <main class="bg-gray-300 h-screen">
    <Tabs {items} {active}/>
  </main>
  <Footer/>
</main>
