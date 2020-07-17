<template>
  <h1>{{ msg }}</h1>
  <div>Dot env variable: {{ dotEnv ? dotEnv : "undefined" }}</div>
  <br>
  <div>Cross env variable: {{ crossEnv ? crossEnv : "undefined" }}</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    }
  },
  setup() {
    const dotEnv = import.meta.env.VITE_DOT_ENV;
    const crossEnv = import.meta.env.VITE_CROSS_ENV;

    return { dotEnv, crossEnv }
  }
}
</script>
