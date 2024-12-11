<template>
  <div class="docs-example">


    <div class="code-toggle-button">
      <KIconButton  class="code-toggle"
      :icon="isCodeVisible ? 'chevronUp' : 'codeToggle'"
      tooltip="Toggle code visibility"
      @click="toggleCodeVisibility"
    />
        </div>

        <!-- Toggle code  -->
    <div v-show="isCodeVisible" class="code-container">
      <slot name="code" />
    </div>

    <!--  The component -->
    <div class="example-container">
      <slot />
    </div>


  </div>
</template>


<script>
  import KIconButton from "../../lib/buttons-and-links/KIconButton.vue";

  export default {
    name: "DocsExample",
    components: {
    KIconButton
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
      margin-bottom: 24px;
      padding-top: 0;
      padding: 20px;

      /* border: 1px solid #ddd; */
      border-radius: 4px;
    }

    .code-toggle-button {
      margin-bottom: 16px;
      display: flex;
      justify-content: flex-end;
    }

    .code-toggle {
      padding: 8px 16px;
      background-color: #f5d858;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .code-toggle:hover {
      background-color: #0056b3;
    }


    .code-container {
     border: none;

    }
    </style>
