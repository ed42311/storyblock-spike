<template>
  <div>
    <component
      v-for="(component, index) in components"
      :is="component.componentName"
      :key="index"
      v-bind="component.props"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { extractComponents } from '@vue-storefront/storyblok'
import Banner from '~/cms/Banner.vue'

interface RenderContent {
  componentName: string
  props?: {}
}

export default Vue.extend({
  name: 'RenderContent',
  components: {
    Banner
  },
  props: {
    content: {
      type: Array,
    },
  },
  computed: {
    components(): RenderContent[] {
      console.log("computed")
      // 4. Storyblok call is getting through...  mapping maybe incorrect ?
      // [                                                                                                                      12:29:31
      //   {
      //     componentName: 'banner',
      //     props: {
      //       _uid: '7f9dc04d-a6e2-475b-ae80-02e480345f17',
      //       image: [Object],
      //       title: 'hello',
      //       subtitle: 'hello',
      //       component: 'banner',
      //       background: 'hello',
      //       banner_text: 'hello',
      //       description: 'hello'
      //     }
      //   }
      // ]
      return extractComponents(this.content)
    },
  },
})
</script>
