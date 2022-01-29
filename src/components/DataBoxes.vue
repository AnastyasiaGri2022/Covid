<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 -->
    <div class="shadow bg-pink-500 p-10 text-center rounded-lg">
      <h3 class="text-4xl font-bold mb-4 text-white">😷CASES</h3>

      <div class="text-2xl mb-4 text-white red-600 ">
        <span class="font-bold">📈New:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl mb-4 text-white">
        <span class="font-bold">📄Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>

    <!-- Box 2 -->
    <div class="bg-indigo-500 p-10 text-center rounded-lg shadow">
      <h3 class="text-4xl text-white font-bold mb-4 ">💀DEATHS</h3>

      <div class="text-2xl mb-4 text-white">
        <span class="font-bold">📈New:</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4 text-white">
        <span class="font-bold">📄Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>

    
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  setup () {
    return {
      numberWithCommas (x) {
        return x.toString()
          .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
      }
    };
  }
};
</script>
