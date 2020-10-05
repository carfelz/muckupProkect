<template>
  <q-page class="flex">
    <q-item>
      <q-item-label
       class="text-h5"
      >
        Select VPSie
      </q-item-label>
    </q-item>
    <q-item
     class="fit row  justify-between VPSCard"

     >
      <VPSCard
       v-for="vps in VPSData"
       :key="vps.Price"
       v-bind="vps"
      />
    </q-item>
  </q-page>
</template>

<script>
import VPSCard from 'components/VPSCard.vue';

export default {
  name: 'PageIndex',

  components:{VPSCard},

  data(){
    return{
      VPSData:[
        {
          name: 'A0',
          memory: '768MB',
          CPU: 1,
          SSD: "10GB",
          Transfer: "1TB",
          Price: "$4.00/Month"
        },
        {
          name: 'A1',
          memory: '1GB',
          CPU: 1,
          SSD: "20GB",
          Transfer: "1TB",
          Price: "$8.00/Month"
        },
        {
          name: 'A2',
          memory: '2GB',
          CPU: 1,
          SSD: "40GB",
          Transfer: "2TB",
          Price: "$16.00/Month"
        },
        {
          name: 'A4',
          memory: '4GB',
          CPU: 2,
          SSD: "40GB",
          Transfer: "3TB",
          Price: "$32.00/Month"
        },

        {
          name: 'A6',
          memory: '6GB',
          CPU: 2,
          SSD: "80GB",
          Transfer: "3TB",
          Price: "$48.00/Month"
        },

        {
          name: 'A8',
          memory: '9GB',
          CPU: 4,
          SSD: "80GB",
          Transfer: "4TB",
          Price: "$32.00/Month"
        },

        {
          name: 'A12',
          memory: '12GB',
          CPU: 4,
          SSD: "100GB",
          Transfer: "5TB",
          Price: "$96.00/Month"
        },

        {
          name: 'A16',
          memory: '16GB',
          CPU: 8,
          SSD: "100GB",
          Transfer: "5TB",
          Price: "$132.00/Month"
        },
      ]
    }
  }
}
</script>
<style scoped>
.VPSCard{
  flex-wrap: wrap !important;
}
</style>
