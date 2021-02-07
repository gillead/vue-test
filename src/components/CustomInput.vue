<template>
  <div class="custom-input">
    <template v-if="rules">

      <ValidationProvider
        :name="placeholder"
        :rules="rules"
        v-slot="{ errors }"
      >
        <label>
        <input :type="type" :placeholder="placeholder"
               :value="value"
               @input="updateName">
        <div class="custom-input__icon"
             v-html="require(`../assets/images/icons/${icon}.svg`)" v-if="icon"/>
        </label>
        <span v-if="errors[0]">
          {{ errors[0] }}
        </span>
      </ValidationProvider>

    </template>
    <template v-else>

      <label>
        <input :type="type" :placeholder="placeholder"
               :value="value"
               @input="updateName">
        <div class="custom-input__icon"
             v-html="require(`../assets/images/icons/${icon}.svg`)" v-if="icon"/>
      </label>

    </template>
  </div>
</template>

<script>
import { Vue, Component, Prop, Emit } from 'vue-property-decorator'

import {
  ValidationProvider,
} from 'vee-validate/dist/vee-validate.full';

@Component({
  components: {
    ValidationProvider,
  },
})
export default class CustomInput extends Vue {
  @Prop(String) value
  @Prop({ default: 'text' }) type
  @Prop(String) placeholder
  @Prop(Object) rules
  @Prop(String) icon

  @Emit()
  updateName(e) {
    this.$emit('input', e.target.value);
  }
}
</script>
