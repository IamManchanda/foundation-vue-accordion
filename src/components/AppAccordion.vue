<template>
  <div class="c-AppAccordion">
    <ul class="accordion">
      <li
        v-for="accordionItem in accordion" 
        class="accordion-item"
        :class="{ 'is-active': accordionItem.isActive }">
        <a :href="accordionItem.href" @click="selectAccordion(accordionItem)" class="accordion-title">{{ accordionItem.name }}</a>
      </li>
      <slot></slot>
    </ul>
  </div>
  
</template>

<script>
export default {
  name: 'c-AppAccordion',
  data() {
    return {
      accordion: [],
    };
  },
  methods: {
    selectAccordion(selectedAccordion) {
      this.accordion.forEach((accordionItem) => {
        /* eslint-disable no-param-reassign */
        if (accordionItem.name === selectedAccordion.name) {
          accordionItem.isActive = true;
        } else {
          accordionItem.isActive = false;
        }
        /* eslint-enable */
      });
    },
  },
  created() {
    this.accordion = this.$children;
  },
};
</script>

<style lang="scss">
</style>