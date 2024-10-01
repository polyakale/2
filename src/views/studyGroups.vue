<template>
  <div class="row text-center">
    <div class="col-6 p-2 my-table">
      <table>
        <thead>
          <th>Student</th>
          <th>Class</th>
          <th>Study group</th>
        </thead>
        <tbody>
          <tr v-for="(student, i) in students" :key="i">
            <td scope="col">{{ student.name }}</td>
            <td scope="col">{{ student.class }}</td>
            <td scope="col">
              <select
                class="form-select"
                v-model="student.studyGroupId"
              >
                <option
                  v-for="(studyGroup, i) in studyGroups"
                  :key="i"
                  :value="studyGroup.id"
                >
                  {{ studyGroup.name }}
                </option>
              </select>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="col-6">
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
        { id: 1, name: "Tom Stephen", class: "3a", studyGroupId: 1 },
        { id: 2, name: "Sara Johnson", class: "1b", studyGroupId: 3 },
        { id: 3, name: "Mike Brown", class: "5c", studyGroupId: 5 },
        { id: 4, name: "Lisa White", class: "2d", studyGroupId: 3 },
        { id: 5, name: "James Smith", class: "7a", studyGroupId: 4 },
        { id: 6, name: "Emma Davis", class: "12b", studyGroupId: 1 },
        { id: 7, name: "David Wilson", class: "6c", studyGroupId: 2 },
        { id: 8, name: "Olivia Taylor", class: "11d", studyGroupId: 2 },
        { id: 9, name: "Sophia Martinez", class: "4a", studyGroupId: 5 },
        { id: 10, name: "Daniel Anderson", class: "9b", studyGroupId: 3 },
        { id: 11, name: "Emily Thomas", class: "1c", studyGroupId: 5 },
        { id: 12, name: "Jacob Jackson", class: "3d", studyGroupId: 3 },
        { id: 13, name: "Ava White", class: "8a", studyGroupId: 2 },
        { id: 14, name: "Isabella Harris", class: "2b", studyGroupId: 4 },
        { id: 15, name: "Mason Clark", class: "10c", studyGroupId: 4 },
        { id: 16, name: "Liam Lewis", class: "4d", studyGroupId: 5 },
        { id: 17, name: "Charlotte Lee", class: "7b", studyGroupId: 2 },
        { id: 18, name: "Noah Hall", class: "5a", studyGroupId: 2 },
        { id: 19, name: "Lucas Allen", class: "12c", studyGroupId: 2 },
        { id: 20, name: "Mia Young", class: "9d", studyGroupId: 1 },
        { id: 21, name: "Ella King", class: "10a", studyGroupId: 5 },
        { id: 22, name: "Aiden Wright", class: "11b", studyGroupId: 3 },
        { id: 23, name: "Sofia Scott", class: "6c", studyGroupId: 4 },
        { id: 24, name: "Jack Green", class: "3a", studyGroupId: 4 },
        { id: 25, name: "Grace Adams", class: "4b", studyGroupId: 1 },
      ],
      studyGroups: [
        {
          id: 1,
          name: "No study group",
        },
        {
          id: 2,
          name: "Singing",
        },
        {
          id: 3,
          name: "Data Science",
        },
        {
          id: 4,
          name: "Soccer",
        },
        {
          id: 5,
          name: "Handball",
        },
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