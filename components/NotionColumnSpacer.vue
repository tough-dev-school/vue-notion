<template>
  <div class="notion-spacer" :style="spacerStyle" />
</template>

<script>
  const baseWidth = 46; // todo: add magic numbers to a config json

  export default {
    computed: {
      spacerStyle() {
        return { width: `${baseWidth}px` };
      },
    },
  };
</script>
