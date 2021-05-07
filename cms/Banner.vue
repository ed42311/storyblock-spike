<template>
  <SfBanner 
    :title="title"
    :subtitle="subtitle"
    :description="description"
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
    subtitle: '',
    description: '',
  }
}
</script>


