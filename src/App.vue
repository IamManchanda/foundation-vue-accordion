<template>
  <div id="app" class="grid-container">
    <div class="grid-x grid-margin-x grid-padding-y">
      <div class="cell">
        <app-accordion>
          <app-accordion-item 
            name="About us" 
            :selected="true"
            :content="content1">
          </app-accordion-item>
          <app-accordion-item 
            name="About our Culture" 
            :content="content2">
          </app-accordion-item>
          <app-accordion-item 
            name="About our vision" 
            :content="content3">
          </app-accordion-item>
        </app-accordion>
      </div>
    </div>
  </div>
</template>

<script>
import AppAccordion from './components/AppAccordion.vue';
import AppAccordionItem from './components/AppAccordionItem.vue';

export default {
  name: 'App',
  data() {
    return {
      content1: `
        <p><strong>About us:</strong> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptates quas, accusantium deleniti praesentium accusamus nostrum, eius corporis incidunt repellendus? Debitis unde et accusantium enim asperiores quibusdam soluta hic, eligendi rerum!</p>
      `,
      content2: `
        <p><strong>About our culture:</strong> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptates quas, accusantium deleniti praesentium accusamus nostrum, eius corporis incidunt repellendus? Debitis unde et accusantium enim asperiores quibusdam soluta hic, eligendi rerum!</p>
      `,
      content3: `
        <p><strong>About our vision:</strong> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptates quas, accusantium deleniti praesentium accusamus nostrum, eius corporis incidunt repellendus? Debitis unde et accusantium enim asperiores quibusdam soluta hic, eligendi rerum!</p>
      `,
    };
  },
  components: {
    AppAccordion,
    AppAccordionItem,
  },
};
</script>

<style lang="scss">
</style>
