<template>
  <div class="form">
    <form id="main" v-cloak>
      <h1>Services</h1>
      <ul>
        <li
          v-for="(service, index) in services"
          v-on:click="toggleActive(service)"
          v-bind:class="{ active: service.active }"
          v-bind:key="index"
        >
          {{ service.name }} <span>{{ service.price }}</span>
        </li>
      </ul>
      <div class="total">
        Total: <span>{{ total() }}</span>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      services: [
        { name: "Web Development", price: 300, active: true },
        { name: "Design", price: 400, active: false },
        { name: "Integration", price: 250, active: false },
        { name: "Training", price: 220, active: false },
      ],
    };
  },
  methods: {
    toggleActive(s) {
      s.active = !s.active;
    },
    total() {
      let total = 0;

      this.services.forEach((s) => {
        if (s.active) {
          total += s.price;
        }
      });
      return total;
    },
  },
};
</script>