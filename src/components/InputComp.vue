<template>
  <div class="input-group">
    <label class="form-label">{{ label }}</label>
    <input
      class="form-input"
      :type="type"
      :placeholder="placeholder"
      :value="value"
      @input="$emit('update:value', $event.target.value)"
      required
    />
  </div>
</template>

<script>
export default {
  name: "InputComp",
  props: {
    label: String,
    placeholder: String,
    value: String,
   type: String,
  },
};
</script>

<style scoped>
.input-group {
  display: flex;
  flex-direction: column;
  margin-bottom: 16px;
  text-align: right;
}

.form-label {
  font-weight: bold;
  margin-bottom: 4px;
  font-size: 14px;
}

.form-input {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 6px;
}
</style>