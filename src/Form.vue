<template>
  <div>
    <div>
      <p>{{checkAge}}</p>
      <pre>
        {{ JSON.stringify(formValues, null, 2) }}
      </pre>
    </div>

    <!-- trim is example of modifier -->
    <form @submit.prevent="submitForm">
      <div>
        <label for="name">Name:</label>
        <input type="text" id="text" v-model.trim.lazy="formValues.name" />
      </div>

      <div>
        <label for="profile">Profile Summary</label>
        <textarea id="profile" v-model="formValues.profileSummary" />
      </div>
      <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
          <option value="">Select a country</option>
          <option value="india">India</option>
          <option value="vietnam">Vietnam</option>
          <option value="singapore">Singapore</option>
        </select>
      </div>

      <div>
        <label for="job-location">Job location</label>
        <select id="job-location" v-model="formValues.jobLocation" multiple>
          <option value="india">India</option>
          <option value="vietnam">Vietnam</option>
          <option value="singapore">Singapore</option>
        </select>
      </div>

      <div>
        <input
          id="remoteWork"
          type="checkbox"
          v-model="formValues.remoteWork"
          true-value="yes"
          false-value="no"
        />
        <label for="remoteWork">Open to remote work?</label>
      </div>

      <div>
        <input
          id="html"
          type="checkbox"
          value="html"
          v-model="formValues.skillSet"
        />
        <label for="html">HTMl</label>
        <input
          id="css"
          type="checkbox"
          value="css"
          v-model="formValues.skillSet"
        />
        <label for="css">CSS</label>
        <input
          id="javaScript"
          type="checkbox"
          value="javaScript"
          v-model="formValues.skillSet"
        />
        <label for="javaScript">HTMl</label>
      </div>

      <div>
        <input type="radio" id="male" name="gender" v-model="formValues.gender" value="male" />
        <label for="male">Male</label><br />
        <input type="radio" id="female" name="gender" v-model="formValues.gender" value="female" />
        <label for="female">Female</label><br />
        <input type="radio" id="other" name="gender" v-model="formValues.gender" value="other" />
        <label for="other">Other</label>
      </div>

      <div>
      <label for="age">Age</label>
      <input type="number" id="age" v-model.number="formValues.age" />
    </div>

      <div><button>Submit</button></div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        gender:''
      },

      datasets:{
        val1:10,
        isOlder:[10,20,30,40,50,60,70]
      }
    };
  },
  methods: {
    submitForm(){
      alert('Form Submitted!')
      // event.preventDefault();
      console.log('value',this.formValues)
    }
  },

  computed:{
    printValue(){
      return this.datasets.val1
    },
    checkAge(){
      return this.datasets.isOlder.filter(age=>age>50)
    }
  }
};
</script>

<style>
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
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
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
