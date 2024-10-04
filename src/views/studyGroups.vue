<template>
  <div class="row text-center">
    <div class="col-md-6 my-table">
      <table>
        <thead>
          <tr>
            <th>
              Student
              <div class="more-student-container">
                <i
                  class="bi bi-plus-circle add-student-button"
                  data-bs-toggle="modal"
                  data-bs-target="#newStudentModal"
                  @click="createNewStudent()"
                ></i>
              </div>
            </th>
            <th>Class</th>
            <th>
              Study Group
              <div class="shuffle-container">
                <i
                  class="bi bi-shuffle shuffle-button"
                  @click="RandomStudentStudyGroupId()"
                ></i>
              </div>
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="student in students" :key="student.id">
            <td>{{ student.name }}</td>
            <td>{{ student.class }}</td>
            <td>
              <div class="select-wrapper">
                <select class="form-select" v-model="student.studyGroupId">
                  <option
                    v-for="studyGroup in studyGroups"
                    :key="studyGroup.id"
                    :value="studyGroup.id"
                  >
                    {{ studyGroup.name }}
                  </option>
                </select>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="col-md-6 card-container">
      <studyGroupCard
        v-for="studyGroup in studyGroups"
        :key="studyGroup.id"
        :studyGroup="studyGroup"
        :students="students"
      />
    </div>
  </div>
  <newStudentModal
    :title="'New Student'"
    :yes="'Yes'"
    :no="'No'"
    @someKindOfAction="newStudentAdd"
  >
    <div>Hello</div>
  </newStudentModal>
</template>

<script>
import studyGroupCard from "@/components/studyGroupCard.vue";
import newStudentModal from "@/components/newStudentModal.vue";
export default {
  data() {
    return {
      students: [
        { id: 1, name: "Tom Stephen", class: "12.C", studyGroupId: 1 },
        { id: 2, name: "Sara Johnson", class: "9.A", studyGroupId: 1 },
        { id: 3, name: "Mike Brown", class: "10.B", studyGroupId: 1 },
        { id: 4, name: "Lisa White", class: "11.B", studyGroupId: 1 },
        { id: 5, name: "James Smith", class: "12.C", studyGroupId: 1 },
        { id: 6, name: "Emma Davis", class: "13.D", studyGroupId: 1 },
        { id: 7, name: "David Wilson", class: "10.B", studyGroupId: 1 },
        { id: 8, name: "Olivia Taylor", class: "11.B", studyGroupId: 1 },
        { id: 9, name: "Sophia Martinez", class: "9.A", studyGroupId: 1 },
        { id: 10, name: "Daniel Anderson", class: "12.C", studyGroupId: 1 },
        { id: 11, name: "Anna Thomas", class: "10.B", studyGroupId: 1 },
        { id: 12, name: "Jacob Jackson", class: "11.B", studyGroupId: 1 },
      ],
      studyGroups: [
        { id: 1, name: "No study group" },
        { id: 2, name: "Soccer" },
        { id: 3, name: "Robotics" },
        { id: 4, name: "Python Programming" },
        { id: 5, name: "Mobile App Development" },
      ],
    };
  },
  methods: {
    RandomStudentStudyGroupId() {
      this.students.forEach((student) => {
        student.studyGroupId =
          Math.floor(Math.random() * this.studyGroups.length) + 1;
      });
    },
    createNewStudent() {},
  },
  components: {
    newStudentModal,
    studyGroupCard,
  },
};
</script>

<style>
</style>