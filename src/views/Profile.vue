<template>
  <div class="about">
    <div>number{{ phoneNumber }}</div>
    <button @click="goBack">Go back</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      phoneNumber: "022222",
    };
  },
  methods: {
    goBack() {
      window.history.length > 1 ? this.$router.go(-1) : this.$router.push("/");
    },
  },
};
</script>