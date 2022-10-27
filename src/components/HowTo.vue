<template>
  <section class="h-screen">
    <div class="h-100 w-100 d-flex justify-center align-center">
      <div class="d-flex justify-center flex-column w-75 align-center h-75">
        <div>
          <p
            class="text-h3 text-center font-weight-bold mb-10 text-decoration-underline"
          >
            HOW TO USE
          </p>
          <div class="d-flex align-center mt-6 justify-center">
            <v-btn color="black" size="small"> 1 </v-btn>
            <p class="text-subtitle-1 text-center mx-5">
              Copy the list of links, it would looks like this
            </p>
          </div>
        </div>
        <textarea
          disabled
          class="w-75 elevation-4 mt-8 rounded px-5"
          rows="10"
          v-on:focus="$event.target.select()"
          ref="text"
        >
sorry, i like you (1nonly)
https://open.spotify.com/track/4Us7Hw8jDC4t1KLfenilv8?si=124d92b83859404c
tonight, pt. II (demxntia)
https://open.spotify.com/track/1KDFTo1pPXuhtQrx9dm16m?si=14c81f02cc6e41ba
Caused Envy. (Summrs)
https://open.spotify.com/track/1i7NOvplsckRLCKRw3iaVv?si=d56cbf31da82459b
Love me please (OCTAVIO the Dweeb)
https://open.spotify.com/track/1Zcl63wm3VxEKnHCMrw5Hv?si=546a233f521240a7
            </textarea
        >
        <v-btn color="black" size="small" class="mt-5" @click="copy">
          Click To Copy
        </v-btn>
        <div class="d-flex align-center mt-6 justify-center">
          <v-btn color="black" size="small"> 2 </v-btn>
          <p class="text-subtitle-1 text-center mx-5">
            Paste down your copied text
          </p>
        </div>
        <div class="d-flex align-center mt-6 justify-center">
          <v-btn color="black" size="small"> 3 </v-btn>
          <p class="text-subtitle-1 text-center mx-5">
            Click on each of the links to go to your site!
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      text: "This will get copied!",
    };
  },
  methods: {
    copy() {
      this.$refs.text.select();
      document.execCommand("copy");
    },
  },
};
</script>
