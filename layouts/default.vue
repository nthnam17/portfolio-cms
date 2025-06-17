<template>
  <SidebarProvider>
    <sidebarCmn />
    <main>
      <SidebarTrigger />
      <slot />
    </main>
  </SidebarProvider>
</template>

<script lang="ts">
import sidebarCmn from "~/components/sidebar/index.vue";
export default defineComponent({
  name: "defaultLayout",
  components: { sidebarCmn },
  setup() {
    return {};
  },
});
</script>
