<template>
  <div v-if="isActive">
    <!-- No HTML Needed here! -->
  </div>
</template>

<script>
export default {
  name: 'c-AppAccordionItem',
  props: {
    name: {
      required: true,
    },
    content: {
      required: true,
    },
    selected: {
      default: false,
    },
  },
  data() {
    return {
      isActive: false,
    };
  },
  computed: {
    href() {
      return `#${this.name.toLowerCase().replace(/ /g, '-')}`;
    },
  },
  mounted() {
    this.isActive = this.selected;
  },
};
</script>

<style lang="scss">
.accordion-content {
  &.is-active {
    display: block;
  }
}
</style>
