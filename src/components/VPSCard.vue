<template>
  <div>
    <q-card
     clickable
     v-ripple
     class="my-card"
     flat
     bordered>
        <q-card-section>
            <div class="text-h6">{{name}}</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
            <div class="text-overline">Memory: {{memory}}</div>
            <div class="text-overline">CPU: {{CPU}}</div>
            <div class="text-overline">SSD: {{SSD}}</div>
            <div class="text-overline">Transfer: {{Transfer}}</div>
        </q-card-section>

        <q-separator inset />

        <q-card-section>
            <div class="text-h4">{{Price}}</div>
        </q-card-section>
    </q-card>
  </div>

</template>

<script>
export default {
    name: 'VPSCard',
    props:{
        name:{
            type: String
        },
        memory:{
            type: String
        },
        CPU:{
            type: String
        },
        SSD:{
            type: String
        },
        Transfer:{
            type: String
        },
        Price:{
            type: String
        }

    },

  data () {
    return {
      expanded: false,
      details: [
           name,
          memory,
          CPU,
          SSD,
          Transfer,
          Price
        ]
      }
  },
  methods:{
      compute(){
          if(!expanded){
              expanded = true
          }else{
              !expanded
          }
      }
  }
}
</script>

<style scoped>
.my-card{
  width: 250px
}

</style>