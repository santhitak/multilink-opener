<template>
  <div class="ma-lg-14 ma-xs-2 text-center h-screen">
    <div class="d-none d-lg-block d-md-none">
      <p class="mx-8 mt-8 text-h2 font-weight-bold">MULTILINK OPENER</p>
    </div>
    <div class="d-none d-md-block d-lg-none">
      <p class="mx-8 mt-8 text-h3 font-weight-bold">MULTILINK OPENER</p>
    </div>
    <div class="d-none d-sm-block d-md-none">
      <p class="mx-8 mt-8 text-h4 font-weight-bold">MULTILINK OPENER</p>
    </div>
    <div class="d-block d-sm-none">
      <p class="mx-8 mt-8 text-h4 font-weight-bold">MULTILINK OPENER</p>
    </div>
    <p class="ma-6 text-subtitle-1 font-weight-light">
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
    <v-card class="container" v-show="link" style="margin-bottom: 4rem">
      <div class="ma-6">
        <v-btn
          class="ma-4"
          v-for="(data, index) in splitLink"
          :key="data"
          :variant="checkHttps(data) ? '' : 'outlined'"
          :class="
            checkHttps(data)
              ? `bg-${
                  color[index % 5]
                } text-decoration-none mx-auto w-auto d-block`
              : 'cursor-normal mx-auto d-block'
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
  name: "UsagePage",
  data() {
    return {
      link: "",
      linkCount: 0,
      color: ["red", "pink", "orange", "blue", "purple"],
    };
  },
  computed: {
    splitLink() {
      return this.link.trim().split(/\r?\n/);
    },
    countLink() {
      for (let i = 0; i < this.splitLink.length; i++) {
        this.splitLink[i].startsWith("https://") ||
        this.splitLink[i].startsWith("http://")
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
