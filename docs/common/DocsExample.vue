<template>
  <div class="docs-example">


    <div class="code-toggle-button">
      <button @click="toggleCodeVisibility">
        <span>&lt;/&gt;</span>
      </button>
    </div>

        <!-- Toggle code  -->
    <div v-if="isCodeVisible" class="code-container">
      <slot name="code" />
    </div>

    <!--  The component -->
    <div class="example-container">
      <slot />
    </div>

    
  </div>
</template>


<script>
  export default {
    name: "DocsExample",
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
    
    button {
      padding: 8px 16px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    
    button:hover {
      background-color: #0056b3;
    }
    
    
    .code-container {
     border: none;
     transition: all 2s ease-in-out; /* Adjusted duration for smoother transition */

    }
    </style>
    