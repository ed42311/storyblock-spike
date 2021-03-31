<template>
  <SfBanner 
    :title="title"
    :subtitle="subtitle"
  />
</template>

<script>
import {
  SfBanner
} from '@storefront-ui/vue';
export default {
  components: {
    SfBanner
  },
  props: {
    title: '',
    subtitle: ''
  }
}
</script>


