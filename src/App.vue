<template>

    <div>
        <h1>Witaj w systemie do logowania  na zajęcia</h1>

        <div v-if="authenticatedUsername">
            <h2>Witaj {{ authenticatedUsername }}</h2>
            <a @click="logOut()">Wyloguj</a>
        </div>

        <div v-else>

          <login-form @login="logMeIn($event)" button-label="Wejdź"></login-form>
          <login-form @login="logMeIn($event)" button-label="Wleć"></login-form>
          <login-form @login="logMeIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>

        </div>

    </div>
</template>

<script>
    import LoginForm from "./LogInForm.vue";
    import "milligram";


    export default {
      components: {LoginForm},


        data() {
            return {
                authenticatedUsername: '',

            }
        },
        methods: {
            logMeIn(username) {
              this.authenticatedUsername = username;
            },
            logIn() {
                this.authenticatedUsername = this.email;
                this.email = '';
            },
            logOut() {
                this.authenticatedUsername = '';
            }

        }
    }
</script>
