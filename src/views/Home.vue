<template>
<div v-if="commandes">
  <SuiviCmd :commandes="commandes" :articles="articles" />
  <InfoLivraison :commandes="commandes" :client="client" />
  <InfoPaiement :commandes="commandes" />
  <TotalCommande :commandes="commandes" :tousprix="articles.map(a => a.prix*a.quantité)" />
  <BesoinAide />
</div>
<div v-else>
  <p>Loading...datas</p>
</div>
</template>

<script>
// @ is an alias to /src
import SuiviCmd from './SuiviCommande.vue'
import InfoLivraison from './InfoLivraison.vue'
import InfoPaiement from './InfoPaiement.vue'
import TotalCommande from './TotalCommande.vue'
import BesoinAide from './BesoinAide.vue'

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
    SuiviCmd,
    InfoLivraison,
    InfoPaiement,
    TotalCommande,
    BesoinAide
  },

  mounted() {
      fetch('https://my-json-server.typicode.com/Lcdevi/tediber-test/db')
        .then(res => res.json())
        .then(data => {
          console.log("data[0] >>>>>>>>>>>> ", data.commandes[0]);
          this.commandes = data.commandes[0];
          this.articles = data.commandes[0].articles;
          if(data.commandes[0].paiement === "visa") {
            this.paiement = "visa"
          } else if(data.commandes[0].paiement === "paypal") {
            this.paiement = "paypal"
          } else {
            this.paiement = "mastercard"
          };
          console.log("data client >>>>>>>>>>>>>>", data.clients)
          console.log("client id >>>>>>>", this.commandes.client_id)
          let indexClient = data.clients.findIndex(i => i.client_id === this.commandes.client_id)
          console.log("indexclient", indexClient)
          console.log("le client >>>>>>>>", data.clients[indexClient])
          this.client = data.clients[indexClient]
        })
        .catch(err => console.log(err.message))
  }

}
</script>


<style>
h2 {
  text-transform: uppercase;
  font-size: 25px;
  letter-spacing: 2px;
  text-align: center;
}

</style>