<template>
  <div class="grid md:grid-cols-3 gap-4">
    <!-- Case Block -->
    <div
      class="flex flex-col text-center bg-indigo-200 p-10 rounded-lg shadow-xl"
    >
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Cases</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>

    <!-- Deaths Block -->
    <div
      class="flex flex-col text-center bg-indigo-300 p-10 rounded-lg shadow-xl"
    >
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Deaths</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>

    <!-- Recovery Block -->
    <div
      class="flex flex-col text-center bg-indigo-200 p-10 rounded-lg shadow-xl"
    >
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Recovered</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewRecovered) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalRecovered) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DataBoxes",
  props: ["stats"],
  setup() {
    return {
      numberWithCommas(x) {
        return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
      },
    };
  },
};
</script>