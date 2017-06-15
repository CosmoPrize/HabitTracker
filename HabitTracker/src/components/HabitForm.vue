<template>
  <div id="habit-form">
    <div>
      <input type="text" placeholder="Habit Title" v-model="newHabit" /><br />
      <input type="number" placeholder="Repetitions" v-model="reps" /><br />
      <button id="creator" @click="addHabit">Add</button>
    </div>
  </div>
</template>

<script>
const colors = [
  "#E45A84",
  "#FFD478",
  "#BA53DE",
  "#393E46",
  "#497285",
  "#3AB1C8",
  "#F5EBEB",
  "#8DC6FF",
  "#B2E672",
  "#B17179"
];

export default {
  name: 'habit-form',
  data () {
    return {
      
    }
  },
  methods: {
    addHabit() {
      if (this.newHabit && this.reps) {
        this.habits.push({
          title: this.newHabit,
          reps: this.reps,
          initial: this.reps,
          complete: 0,
          random: this.colors[Math.floor(Math.random() * this.colors.length)],
          finished: false
        });
      }
      this.newHabit = '';
      this.reps = '';
    }
  }
}
</script>

<style lang="scss">

</style>
