<template>
  <div class="container">
    <div>
      <h1>
        Events
      </h1>
      <EventCard
        v-for="(event, index) in events"
        :key="index"
        :event="event"
        :data-index="index"
      />
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import EventCard from '@/components/EventCard.vue'

export default {
  components: {
    EventCard
  },
  async fetch({ store, error }) {
    try {
      await store.dispatch('events/fetchEvents')
    } catch (e) {
      error({
        statusCode: 503,
        message: 'Unable to fetch data this time, please try again.'
      })
    }
  },
  computed: mapState({
    events: (state) => state.events.events
  }),
  head() {
    return {
      title: 'Event listing'
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
}
</style>
