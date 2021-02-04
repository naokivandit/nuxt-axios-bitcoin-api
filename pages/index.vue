<template>
  <div>
    <table>
      <thead>
        <tr>
          <th>Country</th>
          <th>Rate</th>
          <th>Discription</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(coin) in coins">
          <td> {{ coin.code }}</td>
          <td> {{ coin.rate }}</td>
          <td> {{ coin.description }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
		async asyncData({ $axios }) {
			const url = "https://api.coindesk.com/v1/bpi/currentprice.json";
			const response = await $axios.$get(url);
			return {
				coins: response.bpi
			};
		}
	};
</script>

<style>

</style>
