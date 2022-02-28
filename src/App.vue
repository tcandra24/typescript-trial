<template>
  <div class="app">
    <p>
      <JobList :jobs="jobs" />
    </p>
    <!-- <p>
      {{ user.name }}
      {{ user.job }}
    </p>
    <button @click="changeData('Tralalalaal', 'Frontend Engineer')">
      Change Data
    </button> -->
  </div>
</template>

<script lang="ts">
// Contoh
// let age: string | number = 12

import { defineComponent, ref } from 'vue';
// import { defineComponent, reactive, toRefs, ref } from 'vue';
import JobList from './components/JobList.vue'
import Job from './types/Job'
import User from './types/User'

export default defineComponent({
  name: 'App',
  components: {
    JobList
  },
  setup () {

    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as number | string
    // })
    // state.name = 'shaun'
    // state.age = 26
    // return {
    //   ...toRefs(state)
    // }
    // const name = ref('Link')
    // const age = ref<number | string>(25) // generic argument (disarankan menggunakan refs)
    // return {
    //   name,
    //   age
    // }

    const jobs = ref<Job[]>([
      {
        title: 'farm worker',
        location: 'lon lonm',
        salary: 30000,
        id: '1'
      },
      {
        title: 'farm worker2',
        location: 'lon lonm2',
        salary: 30002,
        id: '2'
      }
    ]) // Array of job object harus di tambah array kosong setelah generic argument Job

    let user = ref<User>({
      id: 1,
      name: 'Tito Candra P',
      address: 'Jl. Krukah Timur',
      child: 100,
      job: 'Software Engineer'
    });

    function changeData(name: string, job: string) {
      user.value.name = name
      user.value.job = job
    }

    return {
      jobs,
      user,
      changeData
    }
  }
});
</script>

<style>

</style>
