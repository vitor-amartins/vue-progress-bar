<template>
  <div id="app">
    <main>
      <header>
        <h1>Scroll Progress Bar</h1>
      </header>
      <ProgressBar :progress="progress" />
      <Post @progressUpdate="setProgress" />
    </main>
  </div>
</template>

<script>
import Post from './components/Post.vue';
import ProgressBar from './components/ProgressBar.vue';

export default {
  name: 'App',
  components: {
    Post,
    ProgressBar,
  },
  data() {
    return {
      progress: 0,
    };
  },
  methods: {
    setProgress(progress) {
      this.progress = progress;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'montserrat', sans-serif;
}

main {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  overflow: hidden;
}

header {
  background-color: #313131;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}

header h1 {
  color: #FFF;
  font-size: 28px;
  text-align: center;
}
</style>
