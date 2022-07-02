<script lang="ts">
    import Rate from "$lib/content/Rate.svelte";
    import Footer from "$lib/footer/Footer.svelte";
    import Header from "$lib/header/Header.svelte";
    import Links from "$lib/header/Links.svelte";
    let condition: number = 2;
</script>


<main>
    <Links {condition} />
    <Header {condition} />
    <Rate />
    <Footer />
</main>


<style>

</style>