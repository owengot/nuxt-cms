<template>
  <article>
    <h1>SKJSKJ</h1>
    <p>{{ body }}
      <br>
      <strong>Posted on <time :datetime="date">{{ date }}</time></strong>
    </p>
    <img :src="thumbnail">
  </article>
</template>

<script>
export default {
  layout: 'about',
  data () {
    return {
      title: '',
      body: '',
      thumbnail: '',
      date: ''
    }
  },
  async asyncData({ params }) {
    // const postPromise = process.BROWSER_BUILD
    //   ? import('~/content/page/posts/' + params.slug + '.json')
    //   : Promise.resolve(
    //       require('~/content/page/posts/' + params.slug + '.json')
    //     );

    let post = await import('~/content/page/posts/' + params.slug + '.json');
    return post;
  }
};
</script>

