<template>
  <div class="card">
    <h3>{{ studyGroup.name }}</h3>
    <div class="card-body">
      <span v-for="(student, i) in StudyGroupStudent" :key="i" :value="student.id"
        >{{ student.name }}<span> | </span>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["studyGroup", "students"],
  computed: {
    StudyGroupStudent(){
      return this.students.filter(g => g.studyGroupId == this.studyGroup.id)
    }
  },
};
</script>

<style>
</style>