<template>
  <SuiviCmd :commandes="commandes" :articles="articles" />
  <InfoLivraison :commandes="commandes" :client="client" />
  <InfoPaiement :commandes="commandes" />
  <TotalCommande :commandes="commandes" :tousprix="articles.map(a => a.prix)" />
  <!-- <div>
    <h3>informations commande:</h3>
    <p> id de la commande: {{ commandes.id_cmd }} </p>
    <p> numéro de commande: {{ commandes.numero_cmd }} </p>
    <p> date de la commande: {{ commandes.date_cmd }} </p>
    <p> date d'expedition: {{ commandes.date_exp }} </p>
    <p> date de récéption: {{ commandes.date_reception }} </p>
    <p> adresse de livraison: {{ commandes.adresse_livraison }} </p>
    <p v-if="this.paiement === 'visa'"> paiement visa </p>
    <p v-if="this.paiement === 'paypal'"> paiment paypal </p>
    <p v-if="this.paiement === 'mastercard'"> paiement mastercard </p>
    <h3>articles:</h3>
    <div v-for="article in articles" :key="article.id_article">
      <p> {{ article.designation }} </p>
      <p> {{ article.prix }} €- </p>
    </div>
    <h3>informations client:</h3>
    <p> id du client: {{ client.client_id }} </p>
    <p> prénom du client: {{ client.client_prenom }} </p>
    <p> nom du client: {{ client.client_nom }} </p>
    <p> client téléphone: {{ client.client_tel }} </p>
  </div> -->
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import SuiviCmd from './SuiviCommande.vue'
import InfoLivraison from './InfoLivraison.vue'
import InfoPaiement from './InfoPaiement.vue'
import TotalCommande from './TotalCommande.vue'

export default {

  name: 'Home',
  
  data() {
    return {
      commandes: [],
      articles: [],
      paiement: "",
      client: {}
    }
  },
  
  components: {
    HelloWorld,
    SuiviCmd,
    InfoLivraison,
    InfoPaiement,
    TotalCommande
  },

  mounted() {
    fetch('http://localhost:3000/commandes')
      .then(res => res.json())
      .then(data => {
        console.log("data[0] >>>>>>>>>>>> ", data[0]);
        this.commandes = data [0];
        this.articles = data[0].articles;
        if(data[0].paiement === "visa") {
          this.paiement = "visa"
        } else if(data[0].paiement === "paypal") {
          this.paiement = "paypal"
        } else {
          this.paiement = "mastercard"
        }
      })
      .catch(err => console.log(err.message))

      fetch('http://localhost:3000/clients')
        .then(res => res.json())
        .then(data => {
          console.log("data clients >>>>>>>>>>", data)
          console.log("client id >>>>>>>", this.commandes.client_id)
          let indexClient = data.findIndex(i => i.client_id === this.commandes.client_id)
          this.client = data[indexClient]
          console.log("le client >>>>>>>>", data[indexClient])
        })
  }

}
</script>


<style>
h2 {
  text-transform: uppercase;
  font-size: 30px;
}

</style>