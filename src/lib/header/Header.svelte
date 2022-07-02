<script lang="ts">
    export let condition: number;
</script>

<header>
    <div id="text"  class="header_text intro_text">
        {#if condition === 1}
            <h1>Hello! I am Nikita Bogdankov. And here you can find exchange rate and information about me </h1>
        {:else if condition === 2}
            <h1 class="extra_padding"> Here is the exchange rate now</h1>
        {:else if condition === 3}
            <h1 class="extra_padding">Hello again! I am Nikita Bogdankov, and it is information about me </h1>    
        {/if}
    </div>

</header>

<style>

    .extra_padding {
        padding-bottom: 70px;
    }

    .header_text {
        margin-top: 60px;
        text-align: center;
    }

    .intro_text {
        line-height: 100px;
        font-size: 50px;
        font-weight: 700;
        font-style: normal;
        padding-right: 20px;
        padding-left: 20px;
        padding-top: 200px;
        padding-bottom: 230px;
        background-color: pink;
        background: linear-gradient(45deg, #6f42c1, #DDEC6A);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
    }

    @media (max-width: 720px) {
        .intro_text {
            font-size: 25px;
            line-height: 50px;
        }
    }


    @media (max-width: 540px) {
    .intro_text {
        font-size: 18px;
        line-height: 50px;
    }
    }

</style>