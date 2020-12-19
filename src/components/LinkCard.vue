<template>
  <div class="link-card">
    <h3>
      <a :href="link">{{ title }}</a>
    </h3>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'LinkCard',
  props: {
    loading: Boolean,
    title: String,
    link: String,
  },
}
</script>

<style scoped>
h3 {
  font-size: 18px;
  padding: 18px 0 0 0;
  margin: 0;
}

h3 a {
  color: #000000;
}

.link-card {
  position: relative;
  background-color: #ffffff;
  border-radius: 10px;
  padding: 0 20px 20px 20px;
  transition: 0.3s;
  background-image: -webkit-repeating-radial-gradient(
    center center,
    rgba(0, 0, 0, 0.1),
    rgba(0, 0, 0, 0.1) 1px,
    transparent 0,
    transparent 100%
  );
  background-size: 20px 20px;
}

.link-card:hover {
  -webkit-box-shadow: 0px 10px 40px -10px #e6e6e6;
  -moz-box-shadow: 0px 10px 40px -10px #e6e6e6;
  box-shadow: 0px 10px 40px -10px #e6e6e6;
}

.link-card p {
  line-height: 25px;
}

.octicon {
  vertical-align: text-top;
}

/* Animations */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
