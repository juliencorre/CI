<script setup lang="ts">
import axios from 'axios';
import { onMounted , reactive } from 'vue';

defineProps<{
  //msg: string;
}>();

const evaluation = reactive(
    {evaluations: {}}
);




const entetes = reactive(
    {entetes:{}}
)


function getLocationDetails() {

  axios({ method: "GET", "url": "http://localhost:5173/eval1.json" }).then(result => {

                console.log(result.data.evaluations);
                evaluation.evaluations = result.data.evaluations;
                console.log(result.data.entetes);
                entetes.entetes = result.data.entetes;

            }, error => {
                console.error(error);
            });

    };

onMounted(() => getLocationDetails())

</script>


<template>



  <table class="table table-bordered table-sm mt-3 table-striped">
    <thead>
      <tr>
        <th scope="col" style="background-color: coral;" class="text-center"   v-for="evaluation in entetes.entetes.evaluation">{{ evaluation }}</th>
        <th scope="col" style="background-color: azure;" class="text-center"   v-for="eleve in entetes.entetes.eleves">{{ eleve }}</th>
      </tr>
    </thead>
    <tbody>
      <!--tr v-for="ligne in evaluation.evaluations">
        <td>{{ ligne.domaine }}</td>
        <td>{{ ligne.champ }}</td>
        <td>{{ ligne.compétence }}</td>
        <td>{{ ligne.compétence_spé }}</td>
        <td class="text-center">
          <select class="form-select form-select-sm text-center" aria-label=".form-select-sm ">
            <option selected>?</option>
            <option value="1">Oui</option>
            <option value="2">Non</option>
          </select>
        </td>
        <td class="text-center">
          <select class="form-select form-select-sm text-center" aria-label=".form-select-sm ">
            <option selected>?</option>
            <option value="1">Oui</option>
            <option value="2">Non</option>
          </select>
        </td>
      </tr-->
      <tr v-for="ligne in evaluation.evaluations">
        <td>{{ ligne.domaine }}</td>
        <td>{{ ligne.champ }}</td>
        <td>{{ ligne.compétence }}</td>
        <td>{{ ligne.compétence_spé }}</td>
        <td class="text-center" v-for="eleve in ligne.eleves">
          <div>
          <input class="input-control" v-model="eleve.resultat" >
        </div>
        </td>
      </tr>
      <!--tr v-for="ligne in evaluation.evaluations">
        <td>test</td>
        <td>test</td>
        <td>test</td>
        <td>test</td>
        <td class="text-center">
          <select class="form-select form-select-sm text-center" aria-label=".form-select-sm ">
            <option selected>?</option>
            <option value="1">Oui</option>
            <option value="2">Non</option>
          </select>
        </td>
        <td class="text-center">
          <select class="form-select form-select-sm text-center" aria-label=".form-select-sm ">
            <option >?</option>
            <option selected value="1">Oui</option>
            <option value="2">Non</option>
          </select>
        </td>
      </tr-->
    </tbody>
  </table>
</template>

<style scoped>
  .form-select{
    padding : 0 0 0 0 ;
    background-image: none;
    width:auto;
    display:initial;
    border:none;
  }

  .input-control{
    border:none;
    width:40px;
    text-align: center;
    background: transparent;
  }
</style>
