<template>
  <div>

    <the-header></the-header>
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

export default {
  components: {
    BadgeList,
    UserInfo,
    TheHeader,
    CourseGoal,
  },
  data() {
    return {
      activeUser: {
        name: 'John Doe',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
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