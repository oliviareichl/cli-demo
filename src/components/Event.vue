<template>
  <article :style="{background: event.background}">
    <div class="name">
      <h3> {{ event.name }} </h3>
      <br />
      <p> {{ event.details }} </p>
    </div>
    <div class="date">
    <p v-if="date > 0"> {{ date }} days left </p>
      <p v-if="date === 0">Today!</p>
      <p v-if="date < 0"> {{ Math.abs(date) }} days ago </p>
    </div>
  </article>
</template>

<script>
export default {
  props: ['event', 'date'],
}
</script>

<style scoped>

article {
  background: #2c3e50;
  display: flex;
  margin: 2rem;
  border-radius: 0.3rem;
}

.name {
  color: whitesmoke;

}

.date {
  color:whitesmoke;
  margin-left: 2rem;

}
</style>
