<template>
  <ul>
    <li v-for="event in events" :key="event.id">
  <Event :event="event" :date="daysLeft(event)">
  </Event>
    </li>
  </ul>
</template>

<script>
import Event from './components/Event.vue'

const eventData = [
  {
    id: 1,
    name: 'Graduation',
    date: '2016-06-30',
    details: 'wow',
    background: '#c9ffaa'
  },
  {
    id: 2,
    name: 'Birthday',
    date: '2023-10-07',
    details: 'party',
    background: '#bf5b63'
  },
  {
    id: 3,
    name: 'Christmas',
    date: '2023-12-24',
    details: 'hoho',
    background: '#fff8aa'
  },
  {
    id: 4,
    name: 'Weekend!',
    date: '2023-01-13',
    details: 'juhu!',
    background: '#e3aaff'
  },
  {
    id: 5,
    name: 'Musical',
    date: '2023-01-12',
    details: 'drinking!',
    background: '#aac8ff'
  },
]
export default {
  components: {
    Event,
  },
  data() {
    return {
      events: eventData,
    }
  },
  methods: {
    daysLeft(event) {
      const Time = Date.parse(event.date) - Date.now();
      const Days = Math.round(Time / (1000 * 60 * 60 * 24));
      return Days;

    }
  },
}
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

li {
  list-style: none;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
