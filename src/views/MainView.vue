<template>
  <div>
    <LandingPage />
    <HowTo id="howto" />
    <UsagePage id="usage" />
  </div>
</template>

<script>
import { defineComponent } from "vue";
import UsagePage from "@/components/UsagePage.vue";
import LandingPage from "@/components/LandingPage.vue";
import HowTo from "@/components/HowTo.vue";

export default defineComponent({
  name: "HomeView",
  components: { UsagePage, LandingPage, HowTo },
});
</script>
