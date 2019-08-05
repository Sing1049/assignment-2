<template>
  <div
    class="card"
    style="width:60%;display:block;margin:10px auto;text-align:left;"
  >
    <div class="card-header">
      sign Up
    </div>
    <div class="card-body">
      <form ref="form" @submit.prevent="onSubmit">
        <div class="form-group">
          <label for="name">Name</label>
          <input
            type="text"
            prop="name"
            v-model="form.name"
            id="name"
            class="form-control"
            requried
          />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input
            type="email"
            prop="pass"
            class="form-control"
            v-model="form.email"
            id="email"
            requried
          />
        </div>
        <div class="form-group">
          <label for="pass">Password</label>
          <input
            type="password"
            prop="pass"
            class="form-control"
            v-model="form.pass"
            id="pass"
            requried
          />
        </div>
        <span style="display:flex;justify-content:flex-end;padding-right:30px;"
          ><button class="btn btn-primary" type="submit">
            Submit
          </button></span
        >
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import { mapState } from "vuex";

export default {
  data() {
    return {
      form: {
        name: "",
        email: "",
        pass: ""
      }
    };
  },
  computed: {
    ...mapState(["users"])
  },
  methods: {
    ...mapActions(["signUp"]),
    ...mapActions(["updateUsers"]),
    onSubmit(form) {
      this.updateUsers({
        Name: this.form.name,
        Email: this.form.email,
        Password: this.form.pass
      });
      // localStorage.Name = this.form.yourName;
      // localStorage.Email = this.form.email;
    }
  }
};
</script>
