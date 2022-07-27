<template>
  <div>
    <UsagePage />
  </div>
</template>

<script>
import { defineComponent } from "vue";
import UsagePage from "@/components/UsagePage.vue";

export default defineComponent({
  name: "HomeView",
  components: { UsagePage },
});
</script>
