<template>
<div v-if="client">
  <SuiviCmd :commandes="commandes" :articles="articles" />
  <InfoLivraison :commandes="commandes" :client="client" />
  <InfoPaiement :commandes="commandes" />
  <TotalCommande :commandes="commandes" :tousprix="articles.map(a => a.prix*a.quantité)" />
  <BesoinAide />
</div>
<div v-else>
  <p>Loading..... datas</p>
</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
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
    HelloWorld,
    SuiviCmd,
    InfoLivraison,
    InfoPaiement,
    TotalCommande,
    BesoinAide
  },

  mounted() {
      fetch('https://my-json-server.typicode.com/Lcdevi/tediber-test/commandes')
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

      fetch('https://my-json-server.typicode.com/Lcdevi/tediber-test/clients')
        .then(res => res.json())
        .then(data => {
          console.log("data clients >>>>>>>>>>", data)
          console.log("client id >>>>>>>", this.commandes.client_id)
          let indexClient = data.findIndex(i => i.client_id === this.commandes.client_id)
          this.client = data[indexClient]
          console.log("le client >>>>>>>>", data[indexClient])
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