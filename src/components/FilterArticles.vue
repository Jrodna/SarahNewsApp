<!-- Dropdowns to select the country, category or source that is being filtered on -->
<!-- If source is selected clear country and category, if either country or category is selected clear source -->
<script></script>
<template>
  <div>Selected: {{ selected }}</div>

  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option value="no">Norway</option>
    <option value="mx">Mexico</option>
    <option value="sk">Slovakia</option>
  </select>
</template>

<style></style>
