<template>
  <div> 
    <TheHeader/>
    <BadgeList/>
    <UserInfo
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
      />
  </div>
  <course-goals>
    <template #default="slotProps">
      <h3>{{ slotProps.item }}</h3>
      <p>{{ slotProps['another-prop'] }}</p>
      </template>
  </course-goals>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import BadgeList from "./components/BadgeList.vue";
import UserInfo from "./components/UserInfo.vue";
import CourseGoals from "./components/CourseGoals.vue";

export default {
  components: {
    TheHeader,
    BadgeList,
    UserInfo,
    CourseGoals,
  },
  name: "App",
  data() {
    return {
      activeUser: {
        name: "Yaroslav",
        description: "Site owner",
        role: "admin",
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul,
li {
  list-style: none;
}
</style>
