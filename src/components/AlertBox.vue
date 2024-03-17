<template>
  <div class="alert-box">
    <strong>This is an Error for Demo Purposes</strong>
    <slot />
  </div>
</template>

<style scoped>
.alert-box {
  background-color: #f8d7da; /* red background */
  color: #721c24; /* text color */
  padding: 10px;
  margin-bottom: 15px;
  border: 1px solid #f5c6cb; /* border */
  border-radius: 4px; /* border radius */
}
</style>
