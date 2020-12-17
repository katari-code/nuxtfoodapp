<template>
  <div>
        <label :for="select">what {{ select }} do you want? </label>

        <select
          @change="$emit('change', $event.target.value)"
          :id="select" :name="select">
           <option value="">please selcting a {{ select }} </option>
           <option value="firsthing">firstting</option>
           <option v-for="option in selectOptions" :key="option" :value="option">
             {{ option }}
           </option>
        </select>
  </div>
</template>

<script>
  export default {
    props: {
      select:{
        type: String,
        default: "cuisine"
      },
      selectOptions: {
        type: Array,
        default: () =>['taco', 'pizza', 'dim sum']
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
