<script lang="ts">
  import {onMount} from "svelte";
  import axios from "axios";

  const endpoint = "https://open.er-api.com/v6/latest/RUB";
  let exchangeRate: {
    rates: any;
  };

  let rounded = function (number: number) {
    return +number.toFixed(2);
  };

  let dollar: number;
  let euro: number;
  let canDollar: number;
  let mark: number;

  onMount(async function () {
    const response = await axios.get(endpoint);
    exchangeRate = response.data;
    const rates = exchangeRate.rates;
    dollar = rounded(1 / rates.USD);
    euro = rounded(1 / rates.EUR);
    canDollar = rounded(1 / rates.CAD);
    mark = rounded(1 / rates.BAM);
  });
</script>

<main>
  <div class="weather">
    <div class="block_info">
      <h2 class="title">Exchange rate</h2>
      <div class="flex_container">
        <div class="left_part">
          <div>
            <span class="just_text">
              One dollar equals {dollar || "please wait"} rubles
            </span>
          </div>
          <div class="margin_up m1">
            <span class="just_text"
              >One euro equals {euro || "please wait"} rubles</span
            >
          </div>
          <div class="margin_up m2">
            <span class="just_text"
              >One canadian dollar equals {canDollar || "please wait"} rubles</span
            >
          </div>
          <div class="margin_up m3">
            <span class="just_text"
              >One Bosnia-Herzegovina Convertible Mark equals {mark ||
                "please wait"} rubles</span
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</main>

<style>
  .title {
    padding-top: 50px;
    font-size: 50px;
    text-align: center;
  }

  .weather {
    margin-bottom: 20px;
  }

  .just_text {
    font-size: 30px;
  }

  .m1 {
    margin-left: 100px;
  }

  .m2 {
    margin-left: 200px;
  }

  .m3 {
    margin-left: 300px;
  }

  .margin_up {
    margin-top: 40px;
  }

  .block_info {
    padding-top: 30px;
    margin-left: 50px;
    margin-top: 10px;
    margin-right: 50px;
  }

  .flex_container {
    display: flex;
    flex-direction: row;
  }

  .left_part {
    width: 100%;
    padding-bottom: 20px;
  }

  @media (max-width: 720px) {
    .title {
      font-size: 20px;
    }

    .just_text {
      font-size: 15px;
    }

    .m1 {
      margin-left: 40px;
    }

    .m2 {
      margin-left: 80px;
    }

    .m3 {
      margin-left: 120px;
    }

    .flex_container {
      flex-direction: column-reverse;
    }

    .left_part {
      width: 100%;
    }
  }

  @media (max-width: 540px) {
    .block_info {
      margin-left: 20px;
      margin-right: 20px;
    }
  }
</style>
