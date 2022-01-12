<template>
  <v-container fluid fill-height>
    <v-row align="center" justify="center">
      <v-col cols="12" sm="10">
        <v-card class="elevation-6 mt-10">
          <v-window v-model="step">
            <v-window-item :value="1">
              <v-row>
                <v-col cols="12" sm="6">
                  <v-card-text class="mt-12">
                    <h3 class="text-center">Login com sua conta</h3>
                    <h4 class="text-center grey--text">Entre com sua conta para continuar negociando
                      <br> e se comunicando com seus amigos
                    </h4>
                    <v-row align="center" justify="center">
                      <v-col cols="12" sm="8">
                        <v-text-field
                          label="Email"
                          outlined
                          dense
                          :color="colorDefault"
                          autocomplete="false"
                          autofocus
                          class="mt-16"></v-text-field>
                          
                        <v-text-field
                          label="Senha"
                          outlined
                          dense
                          :color="colorDefault"
                          autocomplete="false"
                          type="password"></v-text-field>

                          <v-row>
                            <v-col cols="12" sm="9">
                              <v-checkbox label="Manter login" class="mt-n1" :color="colorDefault"></v-checkbox>
                            </v-col>
                            <v-col cols="12" sm="3">
                              <span class="caption" :color="colorDefault">Lembrar senha</span>
                            </v-col>
                          </v-row>

                          <v-btn :color="colorDefault" dark block tile @click.prevent="login">Login</v-btn>

                          <h5 class="text-center grey-text mt-4 mb-3"> ou entre usando</h5>
                          <div class="d-flex justify-space-between align-center mx-16 mb-16">
                            <v-btn depressed outlined color="grey">
                              <v-icon color="red">fab fa-google</v-icon>
                            </v-btn>
                            <v-btn depressed outlined color="grey">
                              <v-icon color="blue">fab fa-facebook-f</v-icon>
                            </v-btn>
                            <v-btn depressed outlined color="grey">
                              <v-icon color="light-blue lighten-3">fab fa-twitter</v-icon>
                            </v-btn>
                          </div>
                      </v-col>
                    </v-row>
                  </v-card-text>
                </v-col>

                <v-col cols="12" sm="6" :class="['rounded-bl-xl']" :style="{'background-color': colorDefault}">
                  <div style="text-align:center; padding:180px 0;">
                    <v-card-text class="white--text">
                      <h2 class="text-center">
                        Você não tem conta?
                      </h2>
                      <h4>
                        Vamos criar sua primeira conta 
                      </h4>
                    </v-card-text>
                    <div class="text-center">
                      <v-btn tile outlined dark @click="step++">CRIAR CONTA</v-btn>
                    </div>
                  </div>
                </v-col>
              </v-row>
            </v-window-item>

            <v-window-item :value="2">
              <v-row>
                <v-col cols="12" sm="6" :class="['rounded-br-xl']" :style="{'background-color': colorDefault}">
                  <div style="text-align:center; padding:180px 0;">
                    <v-card-text class="white--text">
                      <h2 class="text-center"> Voce já tem conta?</h2>
                      <h4 class="text-ceneter"> Entre com sua conta e continue fazendo conversas com seus <br>
                        amigos e negociações com seus clientes
                      </h4>
                    </v-card-text>
                    <div class="text-center">
                      <v-btn tile outlined dark @click="step--">FAZER LOGIN</v-btn>
                    </div>
                  </div>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-card-text class="mt-12">
                    <h2 class="text-center">Entre com uma conta</h2>
                    <h4 class="text-center">
                      Vamos começar criando sua conta <br>
                      para ter sua primeira experiência.
                    </h4>
                    <v-row align="center" justify="center">
                      <v-col cols="12" sm="8">
                        <v-row>
                          <v-col cols="12" sm="6">
                            <v-text-field label="Nome" outlined dense :color="colorDefault" autocomplete="false" class="mt-4"></v-text-field>
                          </v-col>
                          <v-col cols="12" sm="6">
                            <v-text-field label="Sobrenome" outlined dense :color="colorDefault" autocomplete="false" class="mt-4"></v-text-field>
                          </v-col>
                        </v-row>

                        <v-text-field label="Email" outlined dense :color="colorDefault" autocomplete="false"></v-text-field>
                        <v-text-field label="Password" outlined dense :color="colorDefault" type="password"></v-text-field>

                        <v-row>
                          <v-col cols="12" sm="8">
                            <v-checkbox label="Eu aceito os temos e políticas de privacidade." class="mt-n1" :color="colorDefault"></v-checkbox>
                          </v-col>
                          <v-col cols="12" sm="4" class="text-right">
                            <span class="caption ml-n4" :color="colorDefault">Termos e Condições</span>
                          </v-col>
                        </v-row>

                        <v-btn :color="colorDefault" dark block tile>Entrar</v-btn>
                        <h5 class="text-center grey--text mt-4 mb-3"> Ou entre usando</h5>
                        <div class="d-flex justify-space-between align-center mx-10 mb-11">
                          <v-btn depressed outlined color="grey">
                            <v-icon color="red">fab fa-google</v-icon>
                          </v-btn>
                          <v-btn depressed outlined color="grey">
                            <v-icon color="blue">fab fa-facebook-f</v-icon>
                          </v-btn>
                          <v-btn depressed outlined color="grey">
                            <v-icon color="light-blue lighten-3">fab fa-twitter</v-icon>
                          </v-btn>
                        </div>
                      </v-col>
                    </v-row>
                  </v-card-text>
                </v-col>
              </v-row>
            </v-window-item>
          </v-window>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      colorDefault: '#4A148C',
      step: 1
    }),

    props: {
      source: String
    },

    methods:{
      login() {
        this.$router.push({ name: 'Dashboard' })
      }
    }
  }
</script>

<style>
  .v-application .rounded-bl-xl {
    border-bottom-left-radius: 300px !important;
  }
  .v-application .rounded-br-xl {
    border-bottom-right-radius: 300px !important;
  }
</style>
