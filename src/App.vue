<script>
export default {
  name: 'App',
}

</script>

<template>
  <router-view />
</template>

<style>
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */

.signup {
  height: 100vh;
  display: flex;
  flex-direction: column;
  gap: 10px;
  justify-content: center;
  align-items: center;
}

.logo {
  display: flex;
  flex-direction: column;
  gap: 10px;
  justify-content: center;
  align-items: center;
}

.logo h2 {
  font-weight: 700;
  color: rgb(53, 103, 145);
}

.register input {
  width: 300px;
  height: 35px;
  display: flex;
  margin: 0 auto 20px auto;
  border: 1px solid rgb(53, 103, 145);
  border-radius: 5px;
  padding-left: 10px;
}

.register button {
  width: 300px;
  border: none;
  border-radius: 5px;
  background-color: rgb(53, 103, 145);
  color: #fff;
  font-size: 18px;
  padding: 8px 0;
  cursor: pointer;
  display: block;
  margin: 0 auto;
}

.register button:hover {
  background-color: rgb(48, 116, 172);
}

.register .user-login {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 15px;
}

.register p {
  font-size: 16px;
  font-weight: 500;
}

.register a {
  font-size: 18px;
  font-weight: 600;
  text-decoration: underline;
  color: rgb(0, 132, 255);
  padding-left: 7px;
}

.register a:hover {
  transform: scale(1.05);
}

.title {
  text-align: center;
  padding: 20px 0;
}
</style>
