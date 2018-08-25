<template>
  
  <html>
    <body>
      <Header />
      <main>
        <JobDetails v-bind:listing="listing"/>
        <Form />
      </main>
      <Footer />
    </body>
  </html>  
  
</template>

<script>
import Header from './components/Header'
import JobDetails from './components/JobDetails'
import Form from './components/Form'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Header,
    JobDetails,
    Form,
    Footer
  },
  data() {
        return {
            listing: [],
            apiURL: "../static/listing.json"
        }
  },
  created() {
    fetch(this.apiURL)
      .then(response => response.json())
      .then((json) => {
        console.log("here's what we get from our fetch: ", json);
        return json;
      })
      .then(json => this.listing = json)
  }
}
</script>

<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

html {
  margin: 0;
  padding: 0;
}

body {
  margin: 0 1vw 0 1vw;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}

main {
  grid-row: 2/3;
  width: 70%;
  margin: 0 auto;
  padding: 10px;
}

main section {
  grid-column: 2/3;
}

</style>
