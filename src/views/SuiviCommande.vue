<template>
    <div id="suivi-cmd">
        <div class="zigzag-separateur zigzag-top">
            <h2 class="txt-separateur"> suivi de commande </h2>
        </div>
        <div class="main-part">
            <div class="infos part">
                <div class="suivi-infos-div">
                    <p> N° de commande : <span> {{ commandes.numero_cmd }} </span></p>
                    <p> Date de commande : <span> {{ commandes.date_cmd }} </span></p>
                    <p> Date d'expedition : <span> {{ commandes.date_exp }} </span></p>
                </div>
                <div class="divider-accordion"></div>
                <div class="accordion">
                    <input type="checkbox" id="chck1">
                        <label class="accordion-label" for="chck1">Suivi commande</label>
                    <div class="accordion-content">
                        <img v-if="commandes.suivi_cmd === 'step_1'" src="../assets/tediber-etat-livraison-1de4.svg" alt="image etat livraison">
                        <img v-if="commandes.suivi_cmd === 'step_2'" src="../assets/tediber-etat-livraison-2de4.svg" alt="image etat livraison">
                        <img v-if="commandes.suivi_cmd === 'step_3'" src="../assets/tediber-etat-livraison-3de4.svg" alt="image etat livraison">
                        <img v-if="commandes.suivi_cmd === 'step_4'" src="../assets/tediber-etat-livraison-4de4.svg" alt="image etat livraison">
                    </div>
                </div>
                <div class="divider-accordion"></div>
                <div class="accordion">
                    <input type="checkbox" id="chck2">
                        <label class="accordion-label" for="chck2">Informations sur les retours</label>
                    <div class="accordion-content">
                        Informations sur les retours
                    </div>
                </div>
                <div class="divider-accordion"></div>
            </div>
            <div class="articles part">
                <p>ARTICLES ({{articles.length}})</p>
                <div v-for="article in articles" :key="article.id_article" class="article-card">
                    <div>
                        <img :src='article.image' :alt='article.designation'>
                    </div>
                    <div>
                        <h3>{{ article.designation }} tediber</h3>
                        <span> {{ article.prix }} € </span>
                        <p>TAILLE : {{ article.largeur }} x {{ article.longueur }} cm</p>
                        <p>QTE : {{ article.quantité }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['commandes', 'articles']
}
</script>

<style>
.txt-separateur {
    display: flex;
    align-items: center;
    justify-content: center;
}
.txt-separateur::before, .txt-separateur::after {
    content: "";
    height: 1px;
    border-radius: 5px;
    width: 25%;
    margin: 30px;
    background: #dedcdc;
}
.zigzag-separateur {
    padding: 40px;
}
.zigzag-separateur::after {
    display: flex;
    justify-content: center;
    content: url(../assets/zigzag.svg);
    margin: 15px 0 0 0;
}

#suivi-cmd .main-part {
    display: flex;
    justify-content: center;
}
#suivi-cmd .part {
    width: 43vw;
    padding: 20px;
}
#suivi-cmd span {
    font-weight: bold;
}
#suivi-cmd .suivi-infos-div {
    line-height: 2.5;
}

/*  --------- ACCORDEON ----------- */
input {
  position: absolute;
  opacity: 0;
  z-index: -1;
}
.accordion {
  width: 100%;
  color: #2c3e50;
  overflow: hidden;
}
.accordion-content {
    max-height: 0;
    padding: 0 1em;
    color: red;
    background: white;
    transition: all .35s;
}
.accordion-label {
    /* border: 1px solid blue; */
    cursor: pointer;
    width: 100%;
    display: flex;
    justify-content: space-between;
}
.accordion-label::after {
    content: url(../assets/acc-stroke.png);
    cursor: pointer;

}
input:checked ~ .accordion-content {
    max-height: 100vh;
    padding: 1em;
} 
input:checked ~ .accordion-label::after {
    transform: rotate(180deg);
}
/*  --------- ARTICLE CARD ----------- */
.article-card {
    margin: 20px 0;
    box-shadow: 0 0 0.3rem 0 rgb(127 124 137 / 65%);
    padding: 8px;
    display: flex;
    align-items: center;
}
.article-card div {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 0 10px 0 0;
    line-height: 1.5;
}

/* ------- RESPONSIVE DESIGN POUR < 765 -------- */
@media (max-width: 765px) {
    
    .txt-separateur {
        font-size: 22px;
    }
    .txt-separateur::before, .txt-separateur::after {
        content: "";
        height: 1px;
        border-radius: 5px;
        width: 50px;
        background: #dedcdc;
        margin: 0px;
    }
    .zigzag-separateur {
        padding: 10px 0 20px 0;
    }
    #suivi-cmd .main-part {
        flex-direction: column;
    }   
    #suivi-cmd .part {
        width: 100vw;
        padding: 0 20px 20px 20px;
    }
    .zigzag-top {
        padding-top: 40px;
    }
    .accordion-content img {
        width: 80vw;
    }

}

</style>