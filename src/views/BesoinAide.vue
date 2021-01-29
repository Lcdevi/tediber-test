<template>
    <div id="aide">
        <div class="zigzag-separateur">
            <h2 class="txt-separateur">besoin d'aide</h2>
        </div>
        <div class="main-div-aide">
            <div class="accordion-content-aide">
                <div class="divider-accordion"></div>
                <div class="accordion">
                    <input type="checkbox" id="chck3">
                    <div class="label-stroke">
                        <label class="accordion-label" for="chck3">FOIRE AUX QUESTIONS TEDIBER</label>
                    </div>
                    <div class="accordion-content">
                        foire aux questions tediber
                    </div>
                </div>
                <div class="divider-accordion"></div>
                <div class="accordion">
                    <input type="checkbox" id="chck4">
                    <div class="label-stroke">
                        <label class="accordion-label" for="chck4">LA GARANTIE TEDIBER</label>
                    </div>
                    <div class="accordion-content">
                        la garantie tediber
                    </div>
                </div>
                <div class="divider-accordion"></div>
                <div class="accordion">
                    <input type="checkbox" id="chck5">
                    <div class="label-stroke">
                        <label class="accordion-label" for="chck5">REPRISE DE L'ANCIENNE LITERIE</label>
                    </div>
                    <div class="accordion-content">
                        reprise de l'ancienne literie
                    </div>
                </div>
                <div class="divider-accordion"></div>
                <div class="accordion">
                    <input type="checkbox" id="chck6">
                    <div class="label-stroke">
                        <label class="accordion-label" for="chck6">COMMENT FAIRE UN RETOUR ?</label>
                    </div>
                    <div class="accordion-content">
                        comment faire un retour ?
                    </div>
                </div>
                <div class="divider-accordion"></div>
            </div>
        </div>
    </div>
</template>

<style>
#aide {
    margin-bottom: 30px;
}
#aide .main-div-aide {
    /* border: 1px solid red; */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.accordion-content-aide {
    width: 86vw;
    padding: 18px 20px;
}
.divider-accordion {
    height: 1px;
    border-top: 1px solid #2c3e50;
    margin: 10px 0;
}


/* ------- RESPONSIVE DESIGN POUR < 765 (IPAD) -------- */
@media (max-width: 765px) {
    
    .accordion-content-aide {
        padding: 0px;
    }

}

</style>