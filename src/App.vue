<template>
  <div id="app">
    <div class="authorization-page">
      <div class="authorization-block">
        <div class="authorization-block__description">
          <h2 class="authorization-block__title">
            Desire RolePlay
          </h2>
          <p class="authorization-block__text">
            Лучший проект игровых серверов за всю историю GTA V
          </p>
        </div>
        <div class="authorization-block__form">
          <h3 class="authorization-block__form-title">
            Авторизация
          </h3>
          <p class="authorization-block__form-text">
            Если у вас уже существует аккаунт,
            вы можете войти в него
          </p>
          <AuthorizationForm/>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import AuthorizationForm from './components/AuthorizationForm.vue';

@Component({
  components: {
    AuthorizationForm,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss" src="./assets/scss/style.scss"></style>