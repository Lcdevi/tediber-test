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
                <div class="divider-livraison-info"></div>
                <div>
                    <h3>vos coordonnées</h3> <br>
                    <p>{{ client.client_prenom }} {{ client.client_nom }} </p>
                    <p> {{ client.client_tel }} </p>
                </div>
                <div class="divider-livraison-info"></div>
                <div>
                    <h3>livraison éstimée</h3> <br>
                    <p>{{ commandes.date_reception }}</p>
                </div>
                <div class="divider-livraison-info"></div>
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
    margin-bottom: 30px;
}

#info-livraison .main-div {
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
    margin: 10px;
    padding: 0 20px;
}
.divider-livraison-info {
    height: 1px;
    width: 100%;
    border-top: 1px solid #2c3e50;
    display: none;
}

/* ------- RESPONSIVE DESIGN POUR < 765 (IPAD) -------- */
@media (max-width: 765px) {
    #info-livraison .main-content-div div {
        border-left: none;
    }
    #info-livraison .main-content-div div {
        padding: 0;
    }
    #info-livraison .main-content-div {
        flex-wrap: wrap;
    }
    .divider-livraison-info {
        display: block;
    }
}


/* ------- RESPONSIVE DESIGN POUR IPAD - BREAKPOINT A 1113 -------- */
@media (max-width: 1113px) {
    #info-livraison .main-content-div div {
        padding: 5px 5px 5px 10px;
        margin: 5px;
    }
}

</style>