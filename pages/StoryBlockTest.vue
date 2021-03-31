<template>
  <div>
    <div v-if="loading">Loading content...</div>
    
    <!-- 1. Error is possibly blocking render? -->
    <!-- <div v-if="error">{{error}}</div> -->
    <div v-if="content">
      <render-content :content="content.content.body" />
    </div>
  </div>
</template>

<script>
import { onSSR } from '@vue-storefront/core'
import { useContent } from '@vue-storefront/storyblok'
// path to the component that you've just copied
import RenderContent from '~/cms/RenderContent.vue'

export default {
  components: {
    RenderContent
  },
  setup() {
    const { search, content, loading, error } = useContent()

    // get data
    onSSR(async () => {
      await search({ slug: 'home' })
    })

    return {
      content,
      loading,
      error,
    }
  }
}
</script>
