<template>
  <div class="progress-bar">
    <div
      :class="{ 'progress-inner': true, complete: progress === 100 }"
      :style="`width: ${progress}%`"
    >
      <span :class="{ white: progress > 50 }">{{ progress }}%</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'progressbar',
  props: {
    progress: {
      type: Number,
    },
  },
};
</script>

<style>
.progress-bar {
  width: 100%;
  height: 20px;
  background-color: #FFF;
  position: relative;
}

.progress-inner {
  height: 100%;
  background-image: linear-gradient(to right, #ED008D, #2484E4);
  border-radius: 0 10px 10px 0;
}

.progress-inner.complete {
  border-radius: 0;
}

.progress-inner span {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #313131;
  font-size: 14px;
}

.progress-inner span.white {
  color: #FFF;
}
</style>
