<template>
  <div class="row text-center text-color">
    <div class="col-md-6 my-table">
      <table>
        <thead>
          <tr>
            <th>Student</th>
            <th>Class</th>
            <th>Study Group</th>
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

    <div class="col-md-6">
      <studyGroupCard
        v-for="studyGroup in studyGroups"
        :key="studyGroup.id"
        :studyGroup="studyGroup"
        :students="students"
      />
    </div>
  </div>
</template>

<script>
import studyGroupCard from "@/components/studyGroupCard.vue";
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
        { id: 11, name: "Emily Thomas", class: "10.B", studyGroupId: 1 },
        { id: 12, name: "Jacob Jackson", class: "11.B", studyGroupId: 1 },
        { id: 13, name: "Ava White", class: "9.A", studyGroupId: 1 },
        { id: 14, name: "Isabella Harris", class: "13.D", studyGroupId: 1 },
        { id: 15, name: "Mason Clark", class: "12.C", studyGroupId: 1 },
        { id: 16, name: "Liam Lewis", class: "10.B", studyGroupId: 1 },
        { id: 17, name: "Charlotte Lee", class: "9.A", studyGroupId: 1 },
        { id: 18, name: "Noah Hall", class: "11.B", studyGroupId: 1 },
        { id: 19, name: "Lucas Allen", class: "13.D", studyGroupId: 1 },
        { id: 20, name: "Mia Young", class: "12.C", studyGroupId: 1 },
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
  components: {
    studyGroupCard,
  },
};
</script>

<style>
</style>