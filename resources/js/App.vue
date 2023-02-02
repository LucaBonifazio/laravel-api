<template>
    <section>
        <div class="container">
            <h1>Homepage Frontoffice on Vue</h1>

            <ol>
                <li v-for="post in arrPosts" :key="post.id">{{ post.title }}</li>
            </ol>

        </div>
    </section>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
        arrPosts: [],
    };
  },
  created() {
    axios.get('/api/posts')
      .then(response => this.arrPosts = response.data.results);
  }
}
</script>

<style lang="scss">
    @import '~bootstrap/scss/bootstrap';
</style>

