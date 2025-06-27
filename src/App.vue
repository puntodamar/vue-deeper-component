<template>
  <div>

    <the-header></the-header>
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>

    <button @click="setSelectedComponent('active-goal')">Active Goal</button>
    <button @click="setSelectedComponent('manage-goal')">Manage Goal</button>
    <badge-list></badge-list>
    <user-info
        :full-name="activeUser.name"
        :info-text="activeUser.description"
        :role="activeUser.role"
    ></user-info>
    <course-goal #default="slotProps">
      <h2>{{ slotProps.goal }}</h2>
    </course-goal>
  </div>
</template>

<script>
import BadgeList from './components/BadgeList.vue';
import UserInfo from './components/UserInfo.vue';
import TheHeader from './components/TheHeader.vue';
import CourseGoal from "@/components/CourseGoal.vue";
import ActiveGoal from "@/components/ActiveGoal.vue";
import ManageGoal from "@/components/ManageGoal.vue";

export default {
  components: {
    BadgeList,
    UserInfo,
    TheHeader,
    CourseGoal,
    ActiveGoal,
    ManageGoal,
  },
  data() {
    return {
      selectedComponent: 'active-goal',
      activeUser: {
        name: 'John Doe',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(component) {
      this.selectedComponent = component;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>