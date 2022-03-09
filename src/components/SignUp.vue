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
  </form>

  <p>Email - {{ email }}</p>
  <p>Password - {{ password }}</p>
  <p>Role - {{ role }}</p>
</template>

<script>
export default {
  data() {
    return {
      email: "rider@gmail.com",
      password: "",
      role: "developer",
    };
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
  padding: 10px;
  outline: none;
  margin-top: 10px;
  font-size: 20px;
}
</style>