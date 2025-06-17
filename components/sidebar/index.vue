<script>
import {
  Calendar,
  Home,
  Inbox,
  Search,
  Settings,
  AudioWaveform,
  BookOpen,
  Bot,
  Command,
  Frame,
  GalleryVerticalEnd,
  Map,
  PieChart,
  Settings2,
  SquareTerminal,
} from "lucide-vue-next";

// import NavMainCmn from "@/components/sidebar/NavMain.vue";

export default defineComponent({
  name: "sidebarCmn",
  components: {
    Calendar,
    Home,
    Inbox,
    Search,
    Settings,
    AudioWaveform,
    BookOpen,
    Bot,
    Command,
    Frame,
    GalleryVerticalEnd,
    Map,
    PieChart,
    Settings2,
    SquareTerminal,
    // NavMainCmn,
  },
  props: {
    collapsible: {
      type: String,
      default: "icon",
    },
  },
  setup(props, ctx) {
    // const { collapsible } = toRefs(props);
    // Menu items.
    const data = {
      user: {
        name: "shadcn",
        email: "m@example.com",
        avatar: "/avatars/shadcn.jpg",
      },
      teams: [
        {
          name: "Acme Inc",
          logo: GalleryVerticalEnd,
          plan: "Enterprise",
        },
        {
          name: "Acme Corp.",
          logo: AudioWaveform,
          plan: "Startup",
        },
        {
          name: "Evil Corp.",
          logo: Command,
          plan: "Free",
        },
      ],
      navMain: [
        {
          title: "Playground",
          url: "#",
          icon: SquareTerminal,
          isActive: true,
          items: [
            {
              title: "History",
              url: "#",
            },
            {
              title: "Starred",
              url: "#",
            },
            {
              title: "Settings",
              url: "#",
            },
          ],
        },
        {
          title: "Models",
          url: "#",
          icon: Bot,
          items: [
            {
              title: "Genesis",
              url: "#",
            },
            {
              title: "Explorer",
              url: "#",
            },
            {
              title: "Quantum",
              url: "#",
            },
          ],
        },
        {
          title: "Documentation",
          url: "#",
          icon: BookOpen,
          items: [
            {
              title: "Introduction",
              url: "#",
            },
            {
              title: "Get Started",
              url: "#",
            },
            {
              title: "Tutorials",
              url: "#",
            },
            {
              title: "Changelog",
              url: "#",
            },
          ],
        },
        {
          title: "Settings",
          url: "#",
          icon: Settings2,
          items: [
            {
              title: "General",
              url: "#",
            },
            {
              title: "Team",
              url: "#",
            },
            {
              title: "Billing",
              url: "#",
            },
            {
              title: "Limits",
              url: "#",
            },
          ],
        },
      ],
      projects: [
        {
          name: "Design Engineering",
          url: "#",
          icon: Frame,
        },
        {
          name: "Sales & Marketing",
          url: "#",
          icon: PieChart,
        },
        {
          name: "Travel",
          url: "#",
          icon: Map,
        },
      ],
    };
    return {
      data,
      collapsible: props.collapsible,
    };
  },
});
</script>

<template>
  <Sidebar v-bind="collapsible">
    <SidebarHeader>
      <!-- <TeamSwitcher :teams="data.teams" /> -->
    </SidebarHeader>
    <SidebarContent>
      <!-- <NavMainCmn :items="data.navMain" /> -->
      <!-- <NavProjects :projects="data.projects" /> -->
    </SidebarContent>
    <SidebarFooter>
      <!-- <NavUser :user="data.user" /> -->
    </SidebarFooter>
    <SidebarRail />
  </Sidebar>
</template>
