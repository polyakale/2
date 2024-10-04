<template>
  <div v-if="StudyGroupStudent.length > 0" class="card">
    <div class="card-header bg-transparent">
      <h3 class="card-title">{{ studyGroup.name }}</h3>
    </div>
    <div class="card-body">
      <span
        v-for="(student, i) in StudyGroupStudent"
        :key="i"
        class="student-item"
      >
        {{ student.name }}<span v-if="i < StudyGroupStudent.length - 1">,</span>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["studyGroup", "students"],
  computed: {
    StudyGroupStudent() {
      return this.students
      .filter((g) => g.studyGroupId === this.studyGroup.id)
      .sort((a,b) => a.name.localeCompare(b.name));
    },
  },
};
</script>

<style>
</style>
