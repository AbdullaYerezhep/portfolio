<template>
  <li
  :class="[isActive ? 'w-[95%]' : 'w-[2.5%]'] + ' border border-[#E5E5E5] border-r-0 border-l-0 border-t-0 border-b-0'"
 :style="{ backgroundColor: item.color}"
    class="horizontal-collapse__item js-horizontal-collapse-item horizontal-collapse__item overflow-y-scroll"
    tabindex="0"
    role="button"
  >
  <div class="js-horizontal-collapse-item-inner horizontal-collapse__item-inner">
      <div class="horizontal-collapse__inactive-content" :class="[!isActive ? 'flex justify-center' : 'pl-1']" v-html="item.icon"></div>
      <div v-if="isActive" class="horizontal-collapse__active-content" v-html="item.content"></div>
  </div>
  </li>
</template>


<script setup>
import {computed, defineProps} from 'vue'

const props = defineProps({
  item: {
    type: Object,
    default: () => ({})
  },
  key: {
    type: Number,
    default:0
  },
  isActive: {
    type: Boolean,
    default: false
  },
   className: {
    type: String,
    default: ''
  },
  index: {
    type: Number,
    default: 0
  },
  color: {
    type: String,
    default: '#FFFFFF'
  },
});
const computedStyles = computed(() => {
  if (!props.isActive.value) {
    console.log("asdas");
    return {
      display: 'flex',
      justifyContent: 'center',
    };
  } else {
    log("asdas");
    return {
      dispay: 'block'
    };
  }
});

// console.log(props.isActive.valueOf);
</script>

<style>
.horizontal-collapse__active-content{
  display:flex;
}
</style>