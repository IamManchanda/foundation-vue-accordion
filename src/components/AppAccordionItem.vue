<template>
  <div class="accordion-content is-active" v-if="isActive">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'c-AppAccordionItem',
  props: {
    name: {
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
