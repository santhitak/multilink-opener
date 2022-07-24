<template>
  <div class="ma-14 text-center">
    <p class="mx-8 mt-8 text-h2 font-weight-bold">Multi-Link Opener</p>
    <p class="ma-6 text-subtitle-1 text-orange-darken-2 font-weight-light">
      A very shorter time to open all your copied links
    </p>
    <div>
      <v-textarea
        outlined
        label="Paste your links here"
        v-model="link"
        class="my-8"
      />
    </div>
    <v-card class="container" v-show="link">
      <div class="ma-6">
        <v-btn
          class="ma-4"
          v-for="data in splitLink"
          :key="data"
          :variant="checkHttps(data) ? '' : 'outlined'"
          :class="
            checkHttps(data)
              ? 'bg-orange-darken-2 text-decoration-none mx-auto w-auto d-block'
              : ' mx-auto d-block'
          "
          style="max-width: 70%"
        >
          <a
            :href="checkHttps(data) ? data : null"
            target="_blank"
            class="text-truncate"
            :class="checkHttps(data) ? 'text-white' : 'text-black'"
          >
            {{ checkHttps(data) ? data : data }}</a
          >
        </v-btn>
      </div>
    </v-card>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",

  components: {},
  data() {
    return {
      link: "",
      linkCount: 0,
    };
  },
  computed: {
    splitLink() {
      return this.link.split(/\r?\n/);
    },
    countLink() {
      for (let i = 0; i < this.splitLink.length; i++) {
        this.splitLink[i].startsWith("https://")
          ? this.linkCount + 1
          : this.linkCount + 0;
      }
      return this.linkCount;
    },
  },
  methods: {
    checkHttps(data) {
      return data.startsWith("https://") || data.startsWith("http://")
        ? true
        : false;
    },
  },
});
</script>
