<template>
  <div>
    <label :for="id" class="block text-sm font-medium text-gray-700">{{
      label
    }}</label>
    <textarea
      type="text"
      :name="id"
      :id="id"
      :placeholder="placeholder"
      :value="modelValue"
      @input="updateValue"
      autocomplete="off"
      class="mt-2 shadow-sm w-full sm:text-sm border border-gray-300 rounded-md focus:outline-none py-2 px-3 focus:ring-blue-600 focus:ring-1 focus:border-blue-600"
    ></textarea>
  </div>
</template>

<script>
export default {
  name: "BaseTextarea",
  props: ["id", "label", "placeholder", "modelValue"],
  setup(_, { emit }) {
    const updateValue = (event) =>
      emit("update:modelValue", event.target.value);

    return { updateValue };
  },
};
</script>
