<template>
  <div class="hello container p-5">
    <div class="form-card">
      <h2 class="fs-title">
        <a
          target="_blank"
          href="https://www.solutionspirit.com/vue-js-form-validation-using-vuelidate-library/"
        >
          Vue Js Form validation using Vuelidate article
        </a>
      </h2>

      <form @submit.prevent="submitForm" class="mt-5">
        <div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Full name</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                type="text"
                v-model.trim="$v.name.$model"
                :class="{
                  'is-invalid': $v.name.$error,
                  'is-valid': !$v.name.$invalid,
                }"
              />

              <div class="valid-feedback"></div>
              <div class="invalid-feedback">
                <span v-if="!$v.name.required">Full Name is required</span>
                <span v-if="!$v.name.isUnique"
                  >Invalid Full name e-g John Smith</span
                >
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Username</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                type="text"
                v-model.trim="$v.username.$model"
                :class="{
                  'is-invalid': $v.username.$error,
                  'is-valid': !$v.username.$invalid,
                }"
              />

              <div class="valid-feedback"></div>
              <div class="invalid-feedback">
                <span v-if="!$v.username.required">Username is required</span>
                <span v-if="!$v.username.alpha"
                  >Should only contains alphabets</span
                >
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required"> Date</label>
            </div>
            <div class="col-8">
              <div class="input-group">
                <input
                  class="form-control"
                  id="birthdate"
                  v-model.trim="$v.birthdate.$model"
                  :class="{
                    'is-invalid': $v.birthdate.$error,
                    'is-valid': !$v.birthdate.$invalid,
                  }"
                  type="date"
                  placeholder=""
                />

                <div class="valid-feedback"></div>
                <div class="invalid-feedback">
                  <span v-if="!$v.birthdate.required"
                    >Birthdate is required</span
                  >
                </div>
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Email</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                v-model.trim="$v.email.$model"
                :class="{
                  'is-invalid': $v.email.$error,
                  'is-valid': !$v.email.$invalid,
                }"
              />

              <div class="valid-feedback"></div>
              <div class="invalid-feedback">
                <span v-if="!$v.email.required">Email is required</span>
                <span v-if="!$v.email.email"
                  >Invalid Email e-g example@company.com</span
                >
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Url</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                v-model.trim="$v.url.$model"
                :class="{
                  'is-invalid': $v.url.$error,
                  'is-valid': !$v.url.$invalid,
                }"
              />

              <div class="valid-feedback"></div>
              <div class="invalid-feedback">
                <span v-if="!$v.url.required">Url is required</span>
                <span v-if="!$v.url.url">Invalid Url format</span>
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Age</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                v-model.trim="$v.age.$model"
                :class="{
                  'is-invalid': $v.age.$error,
                  'is-valid': !$v.age.$invalid,
                }"
              />

              <div class="valid-feedback">Your age is valid</div>
              <div class="invalid-feedback">
                <span v-if="!$v.age.required">Age is required</span>
                <span v-if="!$v.age.between">Age should be between 15-55</span>
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Phone Number</label>
            </div>
            <div class="col-8">
              <div class="input-group mb-3">
                <input
                  class="form-control"
                  type="text"
                  v-model.trim="$v.mobile.$model"
                  :class="{
                    'is-invalid': $v.mobile.$error,
                    'is-valid': !$v.mobile.$invalid,
                  }"
                />

                <div class="valid-feedback"></div>
                <div class="invalid-feedback">
                  <span v-if="!$v.mobile.required"
                    >Mobile number is required</span
                  >
                  <span v-if="!$v.mobile.numeric"
                    >Mobile number should only be numeric</span
                  >
                  <span v-if="!$v.mobile.minLength"
                    >Mobile number min length should be 3</span
                  >
                  <span v-if="!$v.mobile.maxLength"
                    >Mobile number max length should be 10</span
                  >
                </div>
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Relationship to student</label>
            </div>
            <div class="col-8">
              <div class="form-group">
                <select
                  v-model.trim="$v.relation_to_student.$model"
                  :class="{
                    'is-invalid': $v.relation_to_student.$error,
                    'is-valid': !$v.relation_to_student.$invalid,
                  }"
                  class="form-control select_center_text"
                  id="relationSelect"
                >
                  <option value="Father">Father</option>
                  <option value="Mother">Mother</option>
                  <option value="Brother">Brother</option>
                  <option value="Brother">Cousin</option>
                  <option value="Sister">Sister</option>
                  <option value="Uncle">Uncle</option>
                  <option value="Aunt">Aunt</option>
                </select>

                <div class="valid-feedback"></div>
                <div class="invalid-feedback">
                  <span v-if="!$v.relation_to_student.required"
                    >Relationship to student is required</span
                  >
                </div>
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Password</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                type="password"
                v-model.trim="$v.password.$model"
                :class="{
                  'is-invalid': $v.password.$error,
                  'is-valid': !$v.password.$invalid,
                }"
              />

              <div class="valid-feedback"></div>
              <div class="invalid-feedback">
                <span v-if="!$v.password.required">Password is required</span>
                <span v-if="!$v.password.withUnderScore"
                  >Should contains underscore e-g '_'</span
                >
              </div>
            </div>
          </div>
          <div class="row mb-4">
            <div class="col-4">
              <label class="color_text required">Confirm password</label>
            </div>
            <div class="col-8">
              <input
                class="form-control"
                v-model.trim="$v.confirm_password.$model"
                :class="{
                  'is-invalid': $v.confirm_password.$error,
                  'is-valid':
                    password != '' ? !$v.confirm_password.$invalid : '',
                }"
              />

              <div class="valid-feedback"></div>
              <div class="invalid-feedback">
                <span v-if="!$v.confirm_password.sameAsPassword"
                  >Confirm password does not match</span
                >
                <span v-if="!$v.confirm_password.required"
                  >Confirm Password is required</span
                >
              </div>
            </div>
          </div>
        </div>
        <button type="submit" class="btn btn-success">
          Submit
        </button>
      </form>
    </div>
  </div>
</template>

<script>
//const withSpace = (value) => value.indexOf(" ") !== -1;
const withUnderScore = (value) => value.indexOf("_") >= 0;

import {
  required,
  email,
  minLength,
  maxLength,
  between,
  alpha,
  numeric,
  url,
  sameAs,
} from "vuelidate/lib/validators";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      name: "",
      email: "",
      birthdate: "",
      age: "",
      mobile: "",
      username: "",
      url: "",
      relation_to_student: "",
      password: "",
      confirm_password: "",
    };
  },
  methods: {
    submitForm() {
      this.$v.$touch();

      if (!this.$v.$invalid) {
        // SUCCESS
        alert("Form is valid");
      }
    },
  },
  validations: {
    name: {
      required,
      isUnique(value) {
        if (value === "") return true;
        var re = /^[a-zA-Z]+(?:\s[a-zA-Z]+)+$/;
        return new Promise((resolve) => {
          resolve(re.test(value));
        });
      },
    },
    username: {
      required,
      alpha,
    },
    birthdate: {
      required,
    },
    email: {
      required,
      email,
    },
    age: {
      required,
      between: between(15, 55),
    },
    url: {
      required,
      url,
    },
    relation_to_student: {
      required,
    },
    mobile: {
      required,
      numeric,
      minLength: minLength(3),
      maxLength: maxLength(10),
    },
    password: {
      required,
      withUnderScore,
    },
    confirm_password: {
      required,
      sameAsPassword: sameAs("password"),
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.is-invalid ~ .invalid-feedback,
.is-invalid ~ .invalid-tooltip,
.was-validated :invalid ~ .invalid-feedback,
.was-validated :invalid ~ .invalid-tooltip {
  display: grid !important;
}
</style>
