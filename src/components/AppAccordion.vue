<template>
  <div class="c-AppAccordion">
    <ul class="accordion">
      <li v-for="accordionItem in accordion" 
        class="accordion-item"
        :class="{ 'is-active': accordionItem.isActive }">
        <a :href="accordionItem.href" @click="selectAccordion(accordionItem)" class="accordion-title">{{ accordionItem.name }}</a>
        <div class="accordion-content" :class="{ 'is-active': accordionItem.isActive }" v-html="accordionItem.content"></div>
      </li>
      <slot></slot> <!-- Just to hold accordion item component -->
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
        accordionItem.isActive = (accordionItem.name === selectedAccordion.name);
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