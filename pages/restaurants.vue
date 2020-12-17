<template>
  <div class="container restaurant">
      <div class="restaurantheading">
        <h1>Resturants</h1>
        <Appselect @change="selectedRestaurant = $event" />
        </div>
    <AppRestaurantifo :datasource="filteredRestaurants" />
  </div>
</template>

<script>
import AppRestaurantifo from '@/components/AppRestaurantifo.vue';
import Appselect from '@/components/Appselect.vue';
    import { mapState } from 'vuex';


export default {
  components: {
    AppRestaurantifo,
    Appselect

  },
  data() {
    return{
      selectedRestaurant: ''
    }
  },
  computed: {
    ...mapState(["fooddata"]),
    filteredRestaurants(){
      if (this.selectedRestaurant) {
          return this.fooddata.filter(el =>{
            let name = el.name.toLowerCase();
            return name.includes(this.selectedRestaurant);
          })
      }
      return this.fooddata;
    }
  }
};

</script>

<style lang="scss" scoped>

</style>
