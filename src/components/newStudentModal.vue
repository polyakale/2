<template>
  <div
    class="modal fade"
    id="newStudentModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h2 class="modal-title fs-5" id="exampleModalLabel">{{ title }}</h2>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <slot></slot>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-success"
            data-bs-dismiss="modal"
            @click="onClickYes()"
          >
            {{ yes }}
          </button>
          <button type="button" class="btn btn-danger" data-bs-dismiss="modal">
            {{ no }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  props: ["title", "yes", "no"],
  methods: {
    onClickYes() {
      this.$emit("someKindOfAction");
    },
  },
};
</script>
  
  <style>
</style>