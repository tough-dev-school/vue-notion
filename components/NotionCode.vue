<template>
  <pre
    :class="[
      'notion-code',
      langClass,
    ]"><code :class="langClass"><template v-for="(segment, segmentIndex) in properties.title" :key="segmentIndex">{{ segment[0] }}</template></code></pre>
</template>

<script>
import { defineComponent } from 'vue';
import { Blockable, blockComputed, blockProps } from '../lib/blockable';

export default defineComponent({
  name: 'NotionCode',
  extends: Blockable,
  props: {
    ...blockProps,
    overrideLang: String,
    overrideLangClass: String,
  },
  computed: {
    ...blockComputed,
    lang() {
      return this.overrideLang || this.properties?.language?.[0]?.[0]?.toLowerCase() || 'plaintext';
    },
    langClass() {
      return this.overrideLangClass || `language-${this.lang}`;
    },
  }
});
</script>
