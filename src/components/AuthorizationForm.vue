<template>
  <form action="#" class="authorization-form">
    <CustomInput
        placeholder="Логин"
        icon="man-user"
        v-model="login"
        :rules="{ required: true, alpha: true, max: 10 }"
        name="login"></CustomInput>
    <CustomInput
        type="password"
        placeholder="Пароль"
        icon="lock"
        v-model="password"
        :rules="{ required: true }"
        name="Пароль"></CustomInput>
    <div class="authorization-form__remember">
      <CustomCheckbox
          id="remember"
          label="Запомнить"
      ></CustomCheckbox>
      <a href="#" class="link">Забыли пароль?</a>
    </div>
    <button class="btn" type="submit">
      Войти
    </button>
    <div class="authorization-form__bottom">
      <a href="#" class="link">Нет аккаунта?</a>
      <a href="#" class="link link-color">Зарегистрироваться</a>
    </div>
  </form>
</template>

<script>
import Vue from 'vue'
import Component from 'vue-class-component'
import CustomInput from './CustomInput.vue';
import CustomCheckbox from './CustomCheckbox.vue';

@Component({
  components: {
    CustomInput,
    CustomCheckbox,
  },
})
export default class AuthorizationForm extends Vue {
  login = ''
  password = ''

}
</script>
