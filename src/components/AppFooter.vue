<template>
    <div class="footer">
        <div class="footer__info">
            <div class="contacto">
                <h3>Contacto</h3>
                <p>Tel.: {{telefono}}</p>
            </div>
        </div>
        <div class="derechos">

        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            telefono: '6060-9292 / 4623-7600'
        }
    }
}
</script>
<style>
    .footer{
        background-color: black;
        width: 100%;
    }
    .footer__info{
        width: 95%;
        margin: 0 auto;
    }
    @media (min-width: 992px){
        .footer__info{
            width: 80%;
        }
    }
    .contacto{
        color: rgb(211, 211, 211);
        padding: 20px;
    }
    .contacto h3{
        margin-bottom: 15px;
    }
    .contacto p{
        color: rgb(187, 187, 187);
    }
</style>