<template>
  <SfBanner title="This should be hello" />
</template>

<script>
import {
  SfBanner
} from '@storefront-ui/vue';
export default {
  components: {
    SfBanner
  },
  setup(props) {
    // console.log("banner")
    // console.log(props)
    // banner
    // Props are empty because ?
    // 2. Comp is not registering ?                                                                                                           12:16:57
    // {} 
  }
}
// 3. Why do we need Extend
// import {
//   SfBanner
// } from '@storefront-ui/vue';
// import Vue from 'vue'

// export default Vue.extend({
//   name: 'Banner',
//   props: {
//     title: {},
//     subtitle: {},
//     description: {},
//     banner_text: {},
//     banner_link: {},
//     image: {},
//     background: {}
//   }
// })
</script>


