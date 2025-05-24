<template >
  <v-container fluid>
    <v-card class="tela pa-10 mt-5 mx-auto pt-4"
      elevation="8"
      max-width="550"
      rounded="lg"
      style="position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); z-index: 1;
      backdrop-filter: blur(2px);
" 
         >
      <div class="text-subtitle-1 text-medium-emphasis">
          <v-switch @click="toggleTheme">toggle theme</v-switch>
          <h2>Sua Conta</h2>
      </div>

          <v-text-field
            prepend-inner-icon="mdi-email-outline"
            label="Sua Senha"
            variant="underlined"
          ></v-text-field>
          
          <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
        Password
      </div>

      <v-text-field
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            hint="At least 8 characters"
            label="Sua Senha"
            name="input-10-1"
            variant="underlined"
            @click:append="show1 = !show1"
            prepend-inner-icon="mdi-lock-outline"
             >
      </v-text-field>

      <a
        class="text-caption text-decoration-none text-blue"
        href="#"
        rel="noopener noreferrer"
        target="_blank">
        Forgot login password?
      </a>

      <v-btn
        class="mb-3 mt-5"
        color="blue"
        size="large"
        variant="tonal"
        block>
        login
      </v-btn>
      
      <v-btn class="google"
        color="blue"
        size="large"
        variant="tonal"
      >
      <svg
        version="1.1"
        width="20"
        id="Layer_1"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        x="0px"
        y="0px"
        viewBox="0 0 512 512"
        style="enable-background:new 0 0 512 512;"
        xml:space="preserve"
        
      >
        <path
          style="fill:#FBBB00;"
          d="M113.47,309.408L95.648,375.94l-65.139,1.378C11.042,341.211,0,299.9,0,256
	c0-42.451,10.324-82.483,28.624-117.732h0.014l57.992,10.632l25.404,57.644c-5.317,15.501-8.215,32.141-8.215,49.456
	C103.821,274.792,107.225,292.797,113.47,309.408z"
        ></path>
        <path
          style="fill:#518EF8;"
          d="M507.527,208.176C510.467,223.662,512,239.655,512,256c0,18.328-1.927,36.206-5.598,53.451
	c-12.462,58.683-45.025,109.925-90.134,146.187l-0.014-0.014l-73.044-3.727l-10.338-64.535
	c29.932-17.554,53.324-45.025,65.646-77.911h-136.89V208.176h138.887L507.527,208.176L507.527,208.176z"
        ></path>
        <path
          style="fill:#28B446;"
          d="M416.253,455.624l0.014,0.014C372.396,490.901,316.666,512,256,512
	c-97.491,0-182.252-54.491-225.491-134.681l82.961-67.91c21.619,57.698,77.278,98.771,142.53,98.771
	c28.047,0,54.323-7.582,76.87-20.818L416.253,455.624z"
        ></path>
        <path
          style="fill:#F14336;"
          d="M419.404,58.936l-82.933,67.896c-23.335-14.586-50.919-23.012-80.471-23.012
	c-66.729,0-123.429,42.957-143.965,102.724l-83.397-68.276h-0.014C71.23,56.123,157.06,0,256,0
	C318.115,0,375.068,22.126,419.404,58.936z"
        ></path>
      </svg>

      Google
    </v-btn>  

      <v-card-text class="text-center">
      </v-card-text>
    </v-card>
  </v-container>

</template>

<script setup>
import { useTheme } from 'vuetify'
import { ref } from 'vue'

 const rules = {
    required: value => !!value || 'Required.',
    min: v => v.length >= 8 || 'Min 8 characters',
    emailMatch: () => (`The email and password you entered don't match`),
  }

  const show1 = ref(false)
  const show2 = ref(true)
  const password = ref('Password')

let theme = useTheme()

function toggleTheme () {
    theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}

</script>

<style>
.google{
  width: 100vh;
}
svg{
  margin-right:10px;
}
.v-switch {
  
  color: rgb(31, 122, 248);
  border-radius: 8px;
  height: 60px;
  position: relative;
  left: 94%;
  top: 53px;
}
 .menor input::placeholder{
  background-color: rgba(12, 17, 29, 0.671);
  font-size: smaller;
  font-weight: 300;
}

</style>