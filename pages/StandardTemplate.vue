<template>
  <div>
    <div v-if="loading">Loading content...</div>
    
    <div v-if="content">
      <h1>{{ content.content.heading }}</h1>
      <ul v-for="( thing, index ) in content.content.body.content" :key="index">
        <p>{{ thing }}</p>
        <p>{{ thing.content }}</p>
      </ul>
    </div>
  </div>
</template>

<script>
import { onSSR } from '@vue-storefront/core'
import { useContent } from '@vue-storefront/storyblok'

export default {
  setup(_, context) {
    const { search, content, loading, error } = useContent()
    onSSR(async () => {
      await search({ slug: `/${context.root.$route.path}` })
    })

    return {
      content,
      loading,
      error,
    }
  }
}
</script>
