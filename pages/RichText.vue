<template>
  <div>
    <div v-if="loading">Loading content...</div>
    
    <div v-if="content">
      <rich-text-render-flur :content="content" />
    </div>
  </div>
</template>

<script>
import { onSSR } from '@vue-storefront/core'
import { useContent } from '@vue-storefront/storyblok'
import { defineComponent, ref } from '@vue/composition-api';
import RichTextRenderFlur from '~/components/RichTextRenderFlur.vue';

function renderDocument(richTextDocument) {
  
  throw new Error()
  console.log(richTextDocument);
  // if (Array.isArray(richTextDocument)) {
  //   return renderNodeList(richTextDocument);
  // }

  // return renderNode(richTextDocument);
}

export default {

  setup(_, context) {
    const { search, content, loading, error } = useContent()
    onSSR(async () => {
      await search({ slug: `about-us` })
    })
 
    // renderDocument(content)
    return {
      content,
      loading,
      error,
    }
  },
  components: {
    RichTextRenderFlur
  }
}
</script>