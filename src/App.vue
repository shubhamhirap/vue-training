<template>
  <div>
    <form>
      <div>
        <pre>
          {{ JSON.stringify(formValues, null, 2) }}
        </pre>
      </div>
      <div>
        <label for="name">Name: </label>
        <input type="text" id="name" v-model="formValues.name" />
      </div>
      <div>
        <label for="profile">Profile Summary: </label>
        <textarea id="profile" v-model="formValues.profileSummary" />
      </div>
      <div>
        <label for="country">Country:</label>
        <select name="country" id="country" v-model="formValues.country">
          <option value="">Select a Country</option>
          <option value="India">India</option>
          <option value="USA">USA</option>
          <option value="UK">England</option>
        </select>
      </div>
      <div>
        <label for="jobLocation">Job Locations:</label>
        <select
          name="jobLocation"
          id="jobLocation"
          multiple
          v-model="formValues.jobLocation"
        >
          <option value="pune">Pune</option>
          <option value="banglore">Banglore</option>
          <option value="hyderabad">Hyderabad</option>
          <option value="new york">New York</option>
          <option value="callifornia">Callifornia</option>
          <option value="london">London</option>
        </select>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
      },
    };
  },
  methods: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
label {
  font-weight: bold;
  display: flex;
  margin-top: 5px;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type="text"],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
}
</style>
