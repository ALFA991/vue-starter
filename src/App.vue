<template>

    <div>
        <h1>Witaj w systemie do logowania  na zajęcia</h1>

        <div v-if="authenticatedUsername">
          <log-out-form @logout="logOut($event)" button-label="Wyjdz"></log-out-form>
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
    import LogoutForm from "./LogOutForm.vue";
    import "milligram";
    import LogOutForm from "@/LogOutForm";


    export default {
      components: {LogOutForm, LoginForm},


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
