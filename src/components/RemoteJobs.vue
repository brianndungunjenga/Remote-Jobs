<template>
  <p v-if="isLoading">Loading...</p>
  <hr>
  <div v-for="job in jobs" :key="job.id">
    <h2>Job Position - {{ job.position }}</h2>
    <p>Date Posted - {{ job.date }}  </p>
    <p>Company - {{ job.company }}</p>
    <p>Location - {{ job.location }}  </p>
    <p>Minimum Salary - {{ job.salary_min }}  </p>
    <p>Maximum Salary - {{ job.salary_max }}  </p>
    <hr>
  </div>
</template>

<script>
export default {
    name: 'RemoteJobs',
    data() {
      return {
        jobs: [],
        isLoading: false
      }
    },
    methods: {
      getJobs() {
        this.isLoading = true;

        fetch('https://remoteok.com/api')
        .then(function (response) {
          return response.json()
        })
        .then(data => {
          this.jobs = data.slice(1)
          this.isLoading = false
        })
      }
    },
    mounted() {
      this.getJobs()
    }
}

</script>
