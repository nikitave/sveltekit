<script lang="ts">
  import Header from "$lib/header/Header.svelte";
  import Links from "$lib/header/Links.svelte";
  let condition: number = 1;
</script>

<section>
  <Links {condition} />
  <Header {condition} />
</section>

<style>
</style>
