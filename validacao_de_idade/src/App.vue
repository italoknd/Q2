<template>
  <div>
    <Mensagem :mensagem="aviso" :background="background" v-show="checarIdade" />
    <div class="mb-3 form">
      <label class="form-label">Informe sua idade: </label>
      <input type="number" class="form-control" v-model="idade"/>
      <button
        type="submit"
        class="btn btn-primary mb-3 mt-2"
        @click="checkIdade()"
      >
        Checar Idade
      </button>
    </div>
    <div class="form">
      <p v-show="aviso">Idade informada: {{idade}}</p>
    </div>
  </div>
</template>

<script>
import Mensagem from './components/Mensagem.vue'

export default {
  name: 'App',
  data() {
    return {
      background: '',
      checarIdade: false,
      aviso: '',
      idade: '',
    }
  },
  components: {
    Mensagem
  },
  methods: {
    checkIdade() {
      if (this.idade >= 18) {
        this.aviso = 'Maior de idade'
        this.checarIdade = true
        this.background = '#44AF69'

        setTimeout(() => {
          this.aviso = ''
          this.checarIdade = false
        }, 4000)
      } else {
        this.aviso = 'Menor de idade'
        this.checarIdade = true
        this.background = 'red'

        setTimeout(() => {
          this.aviso = ''
          this.checarIdade = false
        }, 4000)
      }
    }
  }
}
</script>

<style scoped>
* {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
    Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.form {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  flex-direction: column;
  max-width: 400px;
}

label {
  text-align: left !important;
  font-weight: 600;
}

p{
  font-weight: 600;
}
</style>
