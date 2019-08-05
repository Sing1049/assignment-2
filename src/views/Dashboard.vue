<template>
  <div class="card" style="text-align:left;">
    <div class="card-header">
      Dashboard
    </div>
    <div class="card-body">
      <ul style="text-align:left;list-style:none;">
        <li>Name: {{ NameData }}</li>
        <li>Email: {{ EmailData }}</li>
      </ul>
      <a
        @click="remove"
        class="btn btn-primary"
        style="color:white;display:block;margin:0 auto;width:200px;"
        >Clear Data</a
      >
    </div>
  </div>
</template>
<script>
import { mapGetters, mapActions } from "vuex";
import { mapState } from "vuex";

export default {
  computed: {
    ...mapGetters(["getUserName"]),
    ...mapGetters(["getUserEmail"]),
    NameData() {
      console.log(this.getUserName);
      return this.getUserName;
    },
    EmailData() {
      console.log(this.getUserEmail);
      return this.getUserEmail;
    }
  },
  methods: {
    ...mapActions(["removeData"]),
    ...mapActions(["updateUsers"]),
    remove(form) {
      this.removeData({
        Name: null,
        Email: null,
        Password: null
      });
    },
    clearData() {
      localStorage.clear();
    }
  }
};
</script>
