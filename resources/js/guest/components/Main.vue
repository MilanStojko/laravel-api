<template>
  <div>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    getData() {
      axios
        .get("api/post")
        .then((risposta) => {
          this.posts = risposta.data;
          console.log(this.posts);
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
  created() {
    this.getData();
  },
};
</script>
