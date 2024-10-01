<template>
  <div class="card">
    <div class="card-body">
      <h1 class="card-title" v-for="(studyGroup,i) in studyGroups" :key="i">{{studyGroup.name}}</h1>
      <span v-for="(student, i) in students" :key="i" :value="student.studyGroupId">{{ student.name }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["studyGroups", "students"],
  computed: {},
};
</script>

<style>
</style>