<template>
  <div>
    <div>
      <h1>{{ volume }}</h1>
      <button @click="volume += 1">+</button>
      <button @click="volume -= 1">-</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Watcher",
  data() {
    return {
      volume: 0,
    };
  },

  watch: {
   volume(newVal,oldVal){
     if(newVal>oldVal && newVal===10){
       alert('reached')
     }
   }
  },
};
</script>

<style>
</style>