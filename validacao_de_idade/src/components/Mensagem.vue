<template>
  <div :style="{background: background}" class="mensagem">
    <p>{{ mensagem }}</p>
  </div>
</template>

<script>
export default {
  name: 'Mensagem',
  props: {
    mensagem: String,
    background: String
  }
}
</script>

<style scoped>
.mensagem {
  max-width: 400px;
  padding: 0.8em;
  color: white;
  border-radius: 4px;
  box-shadow: 2px 4px 5px rgba(0, 0, 0, 0.315);
  margin: 20px auto;
  animation: fade 4s;
}

p {
  text-align: center;
  font-weight: 600;
  margin: auto;
}

@keyframes fade {
  25% {
    opacity: 1;
    margin: 20px auto;
  }
  50% {
    opacity: 1;
    margin: 20px auto;
  }
  75% {
    opacity: 0;
    margin: 20px auto;
  }
  100% {
    opacity: 0;
    margin: -20px auto;
  }
}
</style>
