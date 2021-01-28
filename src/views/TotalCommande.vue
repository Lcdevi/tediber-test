<template>
    <div id="total-commande">
        <div class="zigzag-separateur">
            <h2 class="txt-separateur">total commande</h2>
        </div>
        <div class="main-div">
            <div class="main-content-div">
                <p @click="addPrices">sous-total </p>
                <div>
                    {{ tousprix.reduce((acc, item) => acc + item, 0) }}
                </div>    
                
                <p>livraison</p>
                <p>TOTAL :</p>
            </div>
        </div>

    </div>
</template>

<script>

export default {
    props: [ 'tousprix' ]
}

</script>

<style>
#total-commande {
    margin-bottom: 40px;
}
#total-commande .main-div {
    border: 1px solid red;
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
}


</style>