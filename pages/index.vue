<template>
  <div>
    <h1>Eventos</h1>
    <EventCard
      v-for="(event, index) in events"
      :key="index"
      :event="event"
      :data-index="index"
    />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
export default {
  head() {
    return {
      title: 'Listagem dos Eventos'
    }
  },
  components: {
    EventCard
  },
  asyncData({ $axios, error }) {
    return $axios
      .get('http://localhost:3000/events')
      .then(response => {
        return {
          events: response.data
        }
      })
      .catch(e => {
        error({
          statusCode: 503,
          message:
            'Não foi possível recuperar os eventos agora. Favor tentar novamente mais tarde!'
        })
      })
  }
}
</script>
