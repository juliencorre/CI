<script setup lang="ts">
import ClasseEval from "./components/ClasseEval.vue";
</script>

<style>

  header{

  }
  td,th{
    font-size:small;
  }
</style>

<template>
  <header>
  <nav class="navbar navbar-expand-lg bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Ma classe</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <a class="nav-link active" aria-current="page" href="#">Evaluations</a>
        <a class="nav-link" href="#">Eleves</a>
        <a class="nav-link" href="#">Compétences</a>
      </div>
    </div>
  </div>
</nav>
</header>

<div class="container-fluid">

    <ClasseEval />


</div>

<!--div class="row">
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>



  <main>
    <TheWelcome />
  </main>

</div-->
</template>
