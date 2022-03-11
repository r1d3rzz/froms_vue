<template>
  <form>
    <label for="">Email</label>
    <input type="email" required v-model="email" />

    <label for="">Password</label>
    <input type="password" required v-model="password" />

    <label for="">Roles</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>

    <div>
      <input type="checkbox" v-model="accept" />
      <label class="checkboxLabel" for="">Accept Terms and Conditions</label>
    </div>

    <div>
      <label for="">Skills</label>
      <input type="text" v-model="skill" @keyup.alt="addSkills" />
      <p class="guide">add skill Press together with Alt + ,</p>
      <div v-for="skill in skills" :key="skill">
        <p>
          {{ skill }}
          <span class="deleteBtn" @click="deleteSkill(skill)">&#x2717;</span>
        </p>
      </div>
    </div>
  </form>

  <p>Email - {{ email }}</p>
  <p>Password - {{ password }}</p>
  <p>Role - {{ role }}</p>
  <p>Accept - {{ accept }}</p>
</template>

<script>
export default {
  data() {
    return {
      email: "rider@gmail.com",
      password: "",
      role: "developer",
      accept: false,
      skill: "",
      skills: [],
    };
  },

  methods: {
    addSkills(e) {
      if (e.key === ",") {
        this.skills.push(this.skill);
        this.skill = "";
      }
    },

    deleteSkill(skill) {
      this.skills = this.skills.filter((loopSkills) => {
        return loopSkills !== skill;
      });
    },
  },
};
</script>

<style>
body {
  background-color: #eee;
}

form {
  background-color: #fff;
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  text-align: left;
  border-radius: 5px;
}

label {
  display: block;
  margin-top: 30px;
  color: #aaa;
  text-transform: uppercase;
}

input,
select {
  border: none;
  border-bottom: 1px solid #aaa;
  width: 100%;
  color: gray;
  padding: 10px 0;
  outline: none;
  margin-top: 10px;
  font-size: 20px;
}

input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin-right: 10px;
}
.checkboxLabel {
  display: inline-block;
}
.deleteBtn {
  cursor: pointer;
  color: red;
}
.guide {
  color: #aaa;
  position: relative;
  top: 1px;
}
</style>