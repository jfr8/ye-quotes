<template>
  <!-- <div id="main">
    <h1>Quote of the day</h1>
    <i>"{{quote}}"</i>
    <i>"{{quote2}}"</i>
    <p> - Ye</p>
  </div> -->
  <div id="container">
    <h1 class="title">Motivation with Ye</h1>
    <h2 class="subtitle">Fetched from Kanye.Rest</h2>
    <div class="columns is-centered">
      <div class="column is-12-mobile is-8-tablet is-6-desktop">
        <div class="card">
          <div class="card-content">
            <p class="title">"{{ quote }}"</p>
            <p class="subtitle">- Kanye West Archive Tweet</p>
          </div>
          <footer class="card-footer">
            <p class="card-footer-item">
              <span>
                View on
                <a href="https://twitter.com/">Twitter</a>
              </span>
            </p>
            <p class="card-footer-item">
              <span> Share on <a href="#">Facebook</a> </span>
            </p>
          </footer>
        </div><br><br>
        <div class="card">
          <div class="card-content">
            <p class="title">"{{ quote2 }}"</p>
            <p class="subtitle">- Kanye West Archive Tweet</p>
          </div>
          <footer class="card-footer">
            <p class="card-footer-item">
              <span>
                View on
                <a href="https://twitter.com/">Twitter</a>
              </span>
            </p>
            <p class="card-footer-item">
              <span> Share on <a href="#">Facebook</a> </span>
            </p>
          </footer>
        </div><br><br>
        <div class="card">
          <div class="card-content">
            <p class="title">"{{ quote3 }}"</p>
            <p class="subtitle">- Kanye West Archive Tweet</p>
          </div>
          <footer class="card-footer">
            <p class="card-footer-item">
              <span>
                View on
                <a href="https://twitter.com/">Twitter</a>
              </span>
            </p>
            <p class="card-footer-item">
              <span> Share on <a href="#">Facebook</a> </span>
            </p>
          </footer>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import axios from "axios";

export default {
  setup() {
    const quote = ref("");
    const quote2 = ref("");
    const quote3 = ref("");

    const fetchFirstQuote = async () => {
      try {
        const response = await axios.get("https://api.kanye.rest");
        quote.value = response.data.quote;
      } catch (error) {
        console.log(error);
      }
    };

    const fetchSecondQuote = async () => {
      try {
        const response = await axios.get("https://api.kanye.rest");
        quote2.value = response.data.quote;
      } catch (error) {
        console.log(error);
      }
    };

    const fetchThirdQuote = async () => {
      try {
        const response = await axios.get("https://api.kanye.rest");
        quote3.value = response.data.quote;
      } catch (error) {
        console.log(error);
      }
    };

    fetchFirstQuote();
    fetchSecondQuote();
    fetchThirdQuote();

    return {
      quote,
      quote2,
      quote3
    };
  },
};
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";


</style>
