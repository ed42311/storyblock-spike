<template>
  <p> <rich-text-renderer v-if="body" :document="body" /></p>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api';

export default defineComponent({
  // components: { RichTextRenderer },
  name: 'RichTextRenderFlur',
  props: {
    content: {
      type: Object,
      required: true
    }
  },
  setup({content}, context) {
    return {
      body: content.content.body
    }
  }
});
</script>