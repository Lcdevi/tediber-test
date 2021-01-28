<template>
    <div id="info-pmt">
        <div class="zigzag-separateur">
            <h2 class="txt-separateur">informations de paiement</h2>
        </div>
        <div class="main-div">
            <div class="main-content-div">
                <div v-if="commandes.paiement === 'visa'">
                    <img src="../assets/logo-CB-visa.svg" alt="visa logo"> VISA                
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [ 'commandes' ]
}
</script>


<style>

#info-pmt {
    margin-bottom: 30px;
}
#info-pmt .main-div {
    /* border: 1px solid red; */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
#info-pmt .main-content-div {
    width: 86vw;
    box-shadow: 0 0 0.3rem 0 rgb(127 124 137 / 65%);
    display: flex;
    padding: 18px 20px;
}
#info-pmt .main-content-div div {
    /* border: 1px solid red; */
    display: flex;
    align-items: center;
}
#info-pmt .main-content-div div img {
    margin: 0 10px 0 0;
}
</style>