<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2> {{ job.title }} in {{ job.location }} </h2>
        <div class="salary">
          <p> {{ job.salary }} rupees </p>
        </div>
        <div class="description">
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit corrupti labore possimus consectetur itaque quibusdam doloribus cupiditate asperiores cumque quaerat voluptates et ipsum provident dolorem fugit inventore quisquam, necessitatibus maxime exercitationem totam accusantium mollitia aliquid! Laudantium voluptas fugiat blanditiis similique. Voluptatum inventore cumque vitae rem consequatur assumenda, velit dolorem soluta.</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '@/types/Job'

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    }
  }
})
</script>

<style scoped>
  .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>
