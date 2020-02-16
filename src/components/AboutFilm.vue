 
<template>
  <div>
    <br />
    <h1>{{filmDetails.Title}}</h1>
    <br />
    <div>
      <b-card :img-src="filmDetails.Poster" img-alt="Card image" img-right img-height="600px">
        <b-card-text>
          <p>Identifiant : {{ $route.params.id }}</p>
          <p>
            <strong>Résumé:</strong>
            {{filmDetails.Plot}}
          </p>
          <p>
            <strong>Date de sortie:</strong>
            {{filmDetails.Released}}
          </p>
          <p>
            <strong>Durée:</strong>
            {{filmDetails.Runtime}}
          </p>
          <p>
            <strong>Genre:</strong>
            {{filmDetails.Genre}}
          </p>
          <p>
            <strong>Réalisateur:</strong>
            {{filmDetails.Director}}
          </p>
          <p>
            <strong>Scénariste:</strong>
            {{filmDetails.Writer}}
          </p>
          <p>
            <strong>Acteurs:</strong>
            {{filmDetails.Actors}}
          </p>
          <p>
            <strong>Produit par:</strong>
            {{filmDetails.Production}}
          </p>
          <p>
            <strong>Notes:</strong>
          </p>
          <p :key="notes.Source" v-for="notes in filmDetails.Ratings">
            {{notes.Source}}
            <br />
            {{notes.Value}}
          </p>
        </b-card-text>
      </b-card>
    </div>
  </div>
</template>

<script>
const axios = require("axios").default;
export default {
  name: "DetailsPage",
  data() {
    return {
      filmId: this.$route.params.id,
      filmDetails: null
    };
  },
  mounted() {
    axios
      .get("http://www.omdbapi.com/?i=" + this.filmId + "&apikey=904eed5c")
      .then(response => (this.filmDetails = response.data));
  }
};
</script>

<style>
p {
  margin-left: 1%;
}
</style>

