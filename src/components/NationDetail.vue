<template>
  <div v-if="showDetail" class="nation-detail">
    <div>
      <div>
        <h3>{{ selected.name }}<span @click="$emit('closeDetail')">X</span></h3>
      </div>
      <img :src="selected.symbol" />
      <p>{{ selected.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    selected:Object,
    showDetail:Boolean,
  }
}
</script>