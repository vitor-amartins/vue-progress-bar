<template>
  <article>
    <div class="content">
      <h2>The Article Title</h2>
      <h3>Subscribe to the channel</h3>
      <!-- eslint-disable-next-line max-len -->
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptate ipsam non dolorem sequi magnam libero nemo neque, consequatur consectetur error praesentium eligendi ab! Sunt itaque tenetur, saepe officia, nemo qui explicabo animi sint earum optio, sapiente molestias! Temporibus optio hic magni reiciendis ducimus placeat error veritatis. Quod esse illo nihil?</p>
      <!-- eslint-disable-next-line max-len -->
      <p>Magni totam ratione cupiditate sit repudiandae recusandae corporis pariatur optio provident nam necessitatibus animi, quaerat et porro nihil quasi officiis atque, vero itaque minima soluta asperiores dolor? Nobis vero, quos laudantium odit doloribus molestiae consectetur ex maxime eos quisquam adipisci similique blanditiis vitae quam cum qui cumque repellat distinctio repellendus.</p>
      <!-- eslint-disable-next-line max-len -->
      <p>Maiores molestias iste laboriosam quidem debitis possimus repellendus obcaecati veritatis at dignissimos! Mollitia, necessitatibus molestias! Illum architecto enim consequatur incidunt itaque et, repellendus obcaecati consectetur fugit facere inventore amet atque dolorem modi odio doloribus error autem dolor cumque deserunt dolores fugiat debitis vero! Praesentium quae rem nostrum excepturi aperiam cupiditate.</p>
      <!-- eslint-disable-next-line max-len -->
      <p>Ut autem beatae pariatur nostrum numquam in minus esse consectetur dignissimos dolore, optio illum commodi dolores neque exercitationem atque dolorem obcaecati error consequuntur eos ab a, veritatis dicta sed! Cum dolore at quos blanditiis delectus qui ab distinctio nesciunt, sed id placeat, architecto voluptatibus vitae unde ut inventore aspernatur accusantium.</p>
      <!-- eslint-disable-next-line max-len -->
      <p>Itaque cumque dolore nesciunt voluptatem, sunt vitae! Asperiores ex voluptatibus officia et repellendus architecto voluptatum temporibus incidunt distinctio placeat illo, laboriosam doloremque. Quo accusantium dolorum neque aliquam natus totam recusandae fugit et est ad molestias at iste saepe assumenda, quam, optio expedita. Dignissimos corrupti laboriosam deserunt qui officia, eaque accusamus!</p>
    </div>
  </article>
</template>

<script>
export default {
  name: 'post',
  mounted() {
    const el = document.querySelector('article');
    el.addEventListener('scroll', () => {
      const { scrollTop, clientHeight, scrollHeight } = el;

      const scrollPercent = Math.round(100 * (scrollTop / (scrollHeight - clientHeight)));

      this.$emit('progressUpdate', scrollPercent);
    });
  },
};
</script>

<style>
article {
  width: 100%;
  flex: 1 1 100%;
  max-height: calc(100vh - 80px);
  background-color: #EEE;
  overflow: scroll;
}

article .content {
  padding: 25px;
}

article .content h2 {
  color: #11224F;
  font-size: 32px;
  font-weight: 900;
  margin-bottom: 10px;
}

article .content h3 {
  color: #676767;
  font-size: 22px;
  font-weight: 300;
  margin-bottom: 30px;
}

article .content p {
  color: #313131;
  font-size: 18px;
  font-weight: 300;
  line-height: 1.5;
  margin-bottom: 15px;
}
</style>
