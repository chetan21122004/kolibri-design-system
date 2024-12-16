<template>

  <div class="docs-example">
    <div class="code-toggle-button">
      <KIconButton
        class="code-toggle"
        :icon="isCodeVisible ? 'chevronUp' : 'codeToggle'"
        tooltip="Toggle code visibility"
        @click="toggleCodeVisibility"
      />
    </div>

    <!-- Toggle code  -->
    <div
      v-show="isCodeVisible"
      class="code-container"
    >
      <slot name="code"></slot>
    </div>

    <!--  The component -->
    <div class="example-container">
      <slot></slot>
    </div>
  </div>

</template>


<script>

  import KIconButton from '../../lib/buttons-and-links/KIconButton.vue';

  export default {
    name: 'DocsExample',
    components: {
      KIconButton,
    },
    data() {
      return {
        isCodeVisible: false,
      };
    },
    methods: {
      toggleCodeVisibility() {
        this.isCodeVisible = !this.isCodeVisible;
      },
    },
  };

</script>


<style scoped>

  .docs-example {
    padding: 20px;
    padding-top: 0;
    margin-bottom: 24px;

    /* border: 1px solid #ddd; */
    border-radius: 4px;
  }

  .code-toggle-button {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 16px;
  }

  .code-toggle {
    padding: 8px 16px;
    color: white;
    cursor: pointer;
    background-color: #f5d858;
    border: none;
    border-radius: 4px;
    transition: background-color 0.3s ease;
  }

  .code-container {
    border: none;
  }

</style>
