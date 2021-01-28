<template>
    <div id="info-livraison">
        <div class="zigzag-separateur">
            <h2 class="txt-separateur">informations sur la livraison</h2>
        </div>
        <div class="main-div">
            <div class="main-content-div">
                <div>
                    <h3>adresse de collecte</h3> <br>
                    <p>POINT RELAIS</p>
                    <p>{{ commandes.adresse_livraison }}</p>
                    <p>{{ commandes.arrondissement }}</p>
                    <p>{{ commandes.ville }}</p>
                    <p>{{ commandes.pays }}</p>
                </div>
                <div>
                    <h3>vos coordonnées</h3> <br>
                    <p>{{ client.client_prenom }} {{ client.client_nom }} </p>
                    <p> {{ client.client_tel }} </p>
                </div>
                <div>
                    <h3>livraison éstimée</h3> <br>
                    <p>{{ commandes.date_reception }}</p>
                </div>
                <div>
                    <h3>mode de livraison</h3> <br>
                    <p v-if="commandes.mode_livraison === 'standard'"> livraison standard en point relais</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['commandes', 'client']
}
</script>


<style>

#info-livraison {
    margin-bottom: 40px;
}

#info-livraison .main-div {
    border: 1px solid red;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

#info-livraison .main-content-div {
    width: 86vw;
    box-shadow: 0 0 0.3rem 0 rgb(127 124 137 / 65%);
    display: flex;
    justify-content: space-between;
}
#info-livraison .main-content-div div:nth-child(1) {
    border: none;
}
#info-livraison .main-content-div div {
    border-left: 1px solid #dedcdc;
    margin: 20px;
    padding: 0 20px;
}

</style>