<script lang="ts">
import { ChevronRight, type LucideIcon, X as xIcon } from "lucide-vue-next";
import type { PropType } from "vue";
type itemsNavType = {
  title: string;
  url: string;
  icon?: LucideIcon;
  isActive?: boolean;
  items?: {
    title: string;
    url: string;
  }[];
};

export default defineComponent({
  name: "NavMainCmn",
  components: { ChevronRight, xIcon },
  props: {
    items: {
      type: Object as PropType<itemsNavType[]>,
      default: () => [],
    },
  },
  setup(props, ctx) {
    const { items } = toRefs(props);
    return {
      items,
    };
  },
});
</script>
<template>
  <SidebarGroup>
    <SidebarGroupLabel>Platform</SidebarGroupLabel>
    <SidebarMenu>
      <Collapsible
        v-for="item in items"
        as-child
        :default-open="item.isActive"
        class="group/collapsible"
      >
        <SidebarMenuItem>
          <CollapsibleTrigger as-child>
            <SidebarMenuButton :tooltip="item.title">
              <component :is="item.icon" v-if="item.icon" />
              <span>{{ item.title }}</span>
              <ChevronRight
                class="ml-auto transition-transform duration-200 group-data-[state=open]/collapsible:rotate-90"
              />
            </SidebarMenuButton>
          </CollapsibleTrigger>
          <CollapsibleContent>
            <SidebarMenuSub>
              <SidebarMenuSubItem
                v-for="subItem in item.items"
                :key="subItem?.title"
              >
                <SidebarMenuSubButton as-child>
                  <a :href="subItem?.url">
                    <span>{{ subItem?.title }}</span>
                  </a>
                </SidebarMenuSubButton>
              </SidebarMenuSubItem>
            </SidebarMenuSub>
          </CollapsibleContent>
        </SidebarMenuItem>
      </Collapsible>
    </SidebarMenu>
  </SidebarGroup>
</template>
