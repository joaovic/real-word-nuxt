<template>
  <div>
    <h1>Evento #{{ id }}</h1>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Evento #' + this.id,
      meta: [
        {
          hid: 'description',
          name: 'description', // <-- moved this over from index.vue
          content: 'Tudo que você precisa saber sobre o evento #' + this.id
        }
      ]
    }
  },
  computed: {
    id() {
      return this.$route.params.id
    }
  }
}
</script>
