<template>
  <div>
    <form @submit="submitForm">
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
      <div>
        <input
          type="checkbox"
          id="remoteWork"
          v-model="formValues.remoteWork"
          true-value="yes"
          false-value="no"
        />
        <label for="remoteWork">Open to Remote Work?</label>
      </div>
      <div>
        <label>Skill Set:</label>
        <input
          type="checkbox"
          id="java"
          value="java"
          v-model="formValues.skillSet"
        />
        <label for="java">Java</label>
        <input
          type="checkbox"
          id="python"
          value="python"
          v-model="formValues.skillSet"
        />
        <label for="python">Python</label>
        <input
          type="checkbox"
          id="c++"
          value="c++"
          v-model="formValues.skillSet"
        />
        <label for="c++">C++</label>
        <input
          type="checkbox"
          id="javascript"
          value="javascript"
          v-model="formValues.skillSet"
        />
        <label for="javascript">Javascript</label>
        <input
          type="checkbox"
          id="php"
          value="php"
          v-model="formValues.skillSet"
        />
        <label for="php">PHP</label>
      </div>
      <div>
        <label>Years Of Experience:</label>
        <input
          type="radio"
          id="0-2"
          value="0-2"
          v-model="formValues.yearsOfExperience"
        />
        <label for="0-2">0-2</label>
        <input
          type="radio"
          id="3-5"
          value="3-5"
          v-model="formValues.yearsOfExperience"
        />
        <label for="3-5">3-5</label>
        <input
          type="radio"
          id="6-9"
          value="6-9"
          v-model="formValues.yearsOfExperience"
        />
        <label for="6-9">6-9</label>
      </div>
      <div>
        <button>Submit</button>
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
        remoteWork: "no",
        skillSet: [],
        yearsOfExperience: "",
      },
    };
  },
  methods: {
    submitForm(e) {
      e.preventDefault();
      console.log(this.formValues);
    },
  },
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
