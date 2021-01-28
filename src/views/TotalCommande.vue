<template>
    <div id="total-commande">
        <div class="zigzag-separateur">
            <h2 class="txt-separateur">total commande</h2>
        </div>
        <div class="main-div">
            <div class="main-content-div">
                <div id="wrap-infos">
                    <div class="single-info">
                        <p>Sous-total </p> 
                        <p>{{ this.soustotal = tousprix.reduce((acc, item) => acc + item, 0) }}</p>
                    </div>
                    <div class="single-info">
                        <p>Livraison</p>
                        <p v-if="commandes.tarif_livraison === 0">GRATUITE</p>
                    </div>
                    <div class="single-info">
                        <p>TOTAL : </p>
                        <p>{{ soustotal + commandes.tarif_livraison}}</p>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>

export default {
    props: [ 'tousprix', 'commandes' ],

    data() {
        return {
            soustotal: 0
        }
    }
}

</script>

<style>
#total-commande {
    margin-bottom: 30px;
}
#total-commande .main-div {
    /* border: 1px solid red; */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
#total-commande .main-content-div {
    width: 86vw;
    box-shadow: 0 0 0.3rem 0 rgb(127 124 137 / 65%);
    display: flex;
    padding: 18px 20px;
    flex-direction: column;
    align-items: center;
}
#total-commande #wrap-infos {
    /* border: 1px solid red; */
    display: flex;
    flex-direction: column;
    width: 180px;
}
#total-commande .single-info {
    /* border: 1px solid green; */
    display: flex;
    justify-content: space-between;
    padding: 4px;
}
#total-commande .single-info:last-child {
    font-weight: bold;
}


/* ------- RESPONSIVE DESIGN POUR IPHONE X - BREAKPOINT A 376 -------- */
@media (max-width: 376px) {
    #total-commande #wrap-infos {
        width: 100%;
    }
}

</style>