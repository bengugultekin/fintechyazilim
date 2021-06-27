<template>
  <b-container>
    <b-row align-v="center">
      <data-list/>
      <!-- <b-col>
        <b-table striped hover :items="items"></b-table>
      </b-col> -->
    </b-row>
  </b-container>
  
</template>

<script>
import DataList from '../components/DataList.vue';

export default {
  // data() {
  //     return {
  //       items: [
  //         { name: 'Afghanistan', capital: 'Kabul', region: 'Asia', flag: '"https://restcountries.eu/data/afg.svg"' },
  //         { name: 'Åland Islands', capital: 'Mariehamn', region: 'Europe', flag:'"https://restcountries.eu/data/ala.svg"' },
  //         { name: 'Albania', capital: 'Tirana', region: 'Europe', flag:'"https://restcountries.eu/data/alb.svg"' },
  //         { name: 'Algeria', capital: 'Algiers', region: 'Africa', flag:'"https://restcountries.eu/data/dza.svg"' }
  //       ]
  //     }
  //   }
  name: "Home",
  components: {'data-list': DataList
    
  },
};
</script>
