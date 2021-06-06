<template>
  <HomePageHero />
  <div class="border-grey-dark border-t mb-10"></div>
  <main v-if="!loading">
    <DataTitle :text="title" :dataDate="dataDate" />

    <div class="mb-10 mt-10 container flex items-center sm:flex-row flex-col">
      <CountrySelect @get-country="getCountryData" :countries="countries" />
      <!-- <button
        @click="clearData"
        v-if="stats.Country"
        class="
        flex items-end
          bg-green-700
          text-white
          rounded
          p-3
          mt-10
          focus:outline-none
          hover:bg-green-600

        "
      >
        Clear
      </button> -->
      <img
        @click="clearData"
        v-if="stats.Country"
        src="../assets/reset.png"
        class="w-8 ml-4 p-1"
        alt=""
      />
    </div>

    <DataBoxes :stats="stats" />
  </main>

  <main class="flex flex-col align-center justify-center text-center" v-else>
    <div class="text-gray-500 text-3xl mt-10 mb-6">Fetching Covid Data</div>

    <img src="../assets/loading.gif" class="w-56 m-auto" alt="" />
  </main>

  <Footer />
</template>

<script>
import DataTitle from "@/components/DataTitle";
import DataBoxes from "@/components/DataBoxes";
import CountrySelect from "@/components/CountrySelect";
import Footer from "@/components/Footer";
import HomePageHero from "@/components/HomePageHero";

export default {
  name: "Home",
  components: {
    DataTitle,
    DataBoxes,
    CountrySelect,
    Footer,
    HomePageHero,
  },

  data() {
    return {
      loading: true,
      title: "Global",
      dataDate: "",
      stats: {},
      countries: [],
    };
  },
  methods: {
    async fetchCovidData() {
      const result = await fetch("https://api.covid19api.com/summary");
      const data = await result.json();
      return data;
    },
    getCountryData(country) {
      this.stats = country;
      this.title = country.Country;
      console.log(country);
    },
    async clearData() {
      this.loading = true;
      const data = await this.fetchCovidData();
      this.title = "Global";
      this.stats = data.Global;
      this.loading = false;
    },
  },

  async created() {
    const data = await this.fetchCovidData();
    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.loading = false;
  },
};
</script>
  