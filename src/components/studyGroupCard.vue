<template>
  <div class="card text-bg-dark">
    <div class="card-header">
      <h3 class="card-title">{{ studyGroup.name }}</h3>
    </div>
    <div class="card-body">
      <span
        v-for="(student, i) in StudyGroupStudent"
        :key="i"
        class="student-item"
      >
        {{ student.name }}
      </span>
    </div>
  </div>
</template>


<script>
export default {
  props: ["studyGroup", "students"],
  computed: {
    StudyGroupStudent() {
      return this.students.filter((g) => g.studyGroupId == this.studyGroup.id);
    },
  },
};
</script>

<style>
</style>