<template>
  <VMain>
    <VContainer
      class="fill-height"
      fluid
    >
      <VRow
        align="center"
        justify="center"
      >
        <VCol
          cols="12"
          sm="8"
          md="4"
        >
          <VCard class="elevation-12">
            <VToolbar flat>
              <VToolbarTitle>{{ $t((loginMode ? 'login' : 'register')) }}</VToolbarTitle>
              <VSpacer />
              <VBtn
                class="ma-2"
                :outlined="loginMode"
                color="indigo"
                @click="switchMode"
              >
                Register
              </VBtn>
              <VBtn
                class="ma-2"
                :outlined="!loginMode"
                color="indigo"
                @click="switchMode"
              >
                Sign in
              </VBtn>
            </VToolbar>
            <VCardText>
              <VForm v-model="formValid">
                <VTextField
                  v-model="email"
                  label="Email"
                  name="login"
                  type="email"
                  required
                  :rules="emailRules"
                  prepend-icon="mdi-account"
                />
                <VTextField
                  id="password"
                  v-model="pass"
                  :label="$t('password')"
                  name="password"
                  prepend-icon="mdi-lock"
                  required
                  :rules="passwordRules"
                  type="password"
                />
                <VTextField
                  v-if="!loginMode"
                  id="password_retype"
                  v-model="pass_re"
                  :label="$t('password_retype')"
                  name="password_retype"
                  prepend-icon="mdi-lock"
                  required
                  type="password"
                />
              </VForm>
            </VCardText>
            <VCardActions>
              <VSpacer />
              <VBtn
                color="primary"
                :disabled="!isValid"
                @click="submitForm"
              >
                {{ $t((loginMode ? 'login' : 'register')) }}
              </VBtn>
            </VCardActions>
          </VCard>
        </VCol>
      </VRow>
    </VContainer>
  </VMain>
</template>

<script>
export default {
    name: 'AppLogin',
    data () {
        return {
            formValid: false,
            loginMode: true,
            email: 'a@a.ru',
            pass: '123123',
            pass_re: '123123',
            emailRules: [
                v => !!v || 'E-mail is required',
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
            passwordRules: [
                v => !!v || 'Password is required',
                v => (v && v.length >= 5) || 'Password must have 5+ characters',
            ],
        };
    },
    computed: {
        isValid () {
            if (!this.formValid) {
                return false;
            }
            if (!this.loginMode) {
                if (this.pass !== this.pass_re) {
                    return false;
                }
            }
            return true;
        }
    },
    methods: {
        switchMode () {
            this.loginMode = !this.loginMode;
        },
        submitForm () {
            const url = this.loginMode ? 'auth/login' : 'auth/register';
            this.askBackend(url, {
                email: this.email,
                password: this.pass,
                re_password: this.pass_re,
            }).then(
                resp => {
                    if (resp.ok) {
                        const rawData = this.parseJwt(resp.token);
                        this.$store.commit('setUserId', rawData.user_id);
                        this.$store.commit('setAuthExpires', rawData.exp);
                        setTimeout(() => {
                            this.$store.commit('setAuth', 1);
                        }, 100);
                    }
                });
        }
    }
};
</script>

