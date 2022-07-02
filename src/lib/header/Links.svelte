<script lang="ts">
    export let condition: number;
</script>


<main>
    <div class="nav_links">
        {#if condition === 1}
            <a href="/ratePage" class="link_to_page">Check exchange rate</a>
            <a href="/about" class="link_to_page">About me</a>
        {:else if condition === 2}  
            <a href="/" class="link_to_page">Return to the main page</a>  
            <a href="/about" class="link_to_page">About me</a>
        {:else if condition === 3}
            <a href="/" class="link_to_page">Return to the main page</a>
            <a href="/ratePage" class="link_to_page">Check exchange rate</a>
        {/if}
    </div>
</main>


<style>
	.link_to_page {
        color: #6c757d;
        background: linear-gradient(45deg, #6f42c1, #DDEC6A);
        border: 0;
        font-family: serif;
        cursor: pointer;
        font-size: 25px;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        text-decoration: none;
        margin-right: 20px;
        opacity: 0.4;
        transition: 0.2s linear;
    }

    .link_to_page:hover {
        opacity: 1;

    }
	
	.nav_links {
        margin-top: 0;
        background: #212529;
        padding-top: 20px;
        z-index: 1000;
        padding-left: 40px;
        width: 100%;
        height: 50px;
		position: fixed;
        left: 0;
        top: 0;
    }

	@media (max-width: 720px) {

		.nav_links {
			font-size: 15px;
			height: 35px;
		}

		.link_to_page {
			font-size: 15px;
		}
	}


	@media (max-width: 540px) {
		.nav_links {
			padding-right: 0;
		}
	}

</style>