<script lang="ts">
  import Info from "$lib/content/Info.svelte";
  import Footer from "$lib/footer/Footer.svelte";
  import Header from "$lib/header/Header.svelte";
  import Links from "$lib/header/Links.svelte";

  let condition: number = 3;
</script>

<main>
  <Links {condition} />
  <Header {condition} />
  <Info />
  <Footer />
</main>

<style>
</style>
