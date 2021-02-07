<template>
  <div class="custom-checkbox">
    <input type="checkbox" :id="id" name="happy" value="yes">
    <label :for="id">
      {{ label }}
    </label>
    <div class="test"></div>
  </div>
</template>

<script>
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component()
export default class CustomCheckbox extends Vue {
  @Prop(String) id
  @Prop(String) label

};
</script>
