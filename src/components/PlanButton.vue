<template>
  <div class="btn-position">
    <span
      class="btn"
      v-for="plan in plans"
      :key="plan"
      :checked="plan.selected"
      @click="select(plan)"
      :class="[this.selectedPlans.includes(plan.label) ? 'btn-selected' : '']"
    >
      {{ plan.label }}
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedPlans: [],
      plans: [
        { id: 1, label: "The Single", selected: false },
        { id: 2, label: "The Curious", selected: false },
        { id: 3, label: "The Addict", selected: false },
      ],
    };
  },
  methods: {
    select(plan) {
      plan.selected = !plan.selected;
      this.selectedPlans.push(plan.label);
      if (this.selectedPlans.length === 2) {
        return this.selectedPlans.splice(-2, 1);
      }
    },
  },
};
</script>

<style scoped>
.btn-position {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}

button {
  font-family: sans-serif;
  font-size: 100%;
  line-height: 1.15;
  margin: 0;
  width: 20rem;
  margin-top: 0.5rem;
  cursor: pointer;
}

h1,
h2,
h3,
p {
  margin: 0;
}

img {
  border-style: solid;
}

textarea {
  resize: vertical;
}

img {
  max-width: 100%;
  height: auto;
}

.container {
  width: 100%;
}

@media (min-width: 576px) {
  .container {
    max-width: 576px;
  }
}

@media (min-width: 768px) {
  .container {
    max-width: 768px;
  }
}

@media (min-width: 992px) {
  .container {
    max-width: 992px;
  }
}

@media (min-width: 1200px) {
  .container {
    max-width: 1200px;
  }
}

.mx-auto {
  margin-left: auto;
  margin-right: auto;
}

.py-6 {
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
}

.w-1\/3 {
  width: 33.33333%;
}

.w-2\/3 {
  width: 66.66667%;
}

#app {
  height: 74rem;
  -webkit-font-smoothing: auto;
  -moz-osx-font-smoothing: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-family: Roboto, sans-serif;
  background-color: #ccdcdc;
  background-image: url("@//assets/coffee.jpg");
  background-repeat: no-repeat;
  background-position: 100% 100%;
}

.content {
  margin-left: auto;
  margin-right: auto;
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
}

h1.title {
  text-align: center;
  font-size: 1.875rem;
  font-weight: 500;
  color: #2d3336;
}

h2.subtitle {
  margin: 0.7rem auto;
  font-weight: 300;
  font-size: 1.5rem;
  text-align: center;
  line-height: 1.5;
  letter-spacing: 0;
  max-width: 500px;
  color: #5c6162;
}

span#logo {
  font-weight: 700;
  text-transform: uppercase;
  color: #5c6162;
  font-size: 0.875rem;
  letter-spacing: 0.05em;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  padding-bottom: 1rem;
}

.btn {
  display: inline-block;
  color: #fff;
  background-color: #09848d;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  border-radius: 0.25rem;
  text-transform: uppercase;
  font-weight: 500;
  font-size: 0.875rem;
  border-width: 2px;
  border-color: #09848d;
  letter-spacing: 0.2;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  cursor: pointer;
  margin-top: 0.5rem;
}

.btn:hover {
  background: rgba(37, 142, 149, 0.96);
  border-color: rgba(37, 142, 149, 0.96);
}

.btn:disabled {
  background-color: #127077;
  border-color: #127077;
  color: #9fc1c3;
}

a:not(.btn):hover {
  color: #127077;
  text-decoration: underline;
}

.btn-selected {
  background-color: gray;
}
</style>
