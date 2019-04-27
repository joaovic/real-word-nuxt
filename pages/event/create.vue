<template>
  <div>
    <h1>Criar um Evento</h1>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Criação de Evento',
      meta: [
        {
          hid: 'description',
          name: 'description', // <-- moved this over from index.vue
          content: 'Crie um novo evento na sua visinhança'
        }
      ]
    }
  }
}
</script>
