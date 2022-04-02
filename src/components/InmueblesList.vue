<template>
    <div>
        <div class="dptos-container">
            <div class="dpto" v-for="dpto of infoDptos" v-bind:key="dpto.id" @click="inmuebleRedirect(dpto.id)">
                <div class="dpto__img">
                    <img class="portada-propiedad" :src="dpto.portada" alt="">
                    <img class="vende-alquila" v-show="dpto.vende" src="../assets/estado-inmueble/vende.png" alt="vende">
                    <img class="vende-alquila" v-show="!dpto.vende" src="../assets/estado-inmueble/alquila.png" alt="alquila">
                </div>
                <div class="dpto__info">
                    <p class="dpto__info--titulo">{{dpto.titulo}}</p>
                    <div class="dpto__info--ubi icon-text-block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="dpto__info--ubi--icon icon icon-tabler icon-tabler-map-pin" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#666" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <circle cx="12" cy="11" r="3" />  <path d="M17.657 16.657l-4.243 4.243a2 2 0 0 1 -2.827 0l-4.244 -4.243a8 8 0 1 1 11.314 0z" /></svg>
                            <p class="dpto__info--ubi--text">{{dpto.ubicacion}}</p>
                        </div>
                    <div class="icons-info--container">
                        
                        <div class="dpto__info--sup icon-text-block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="dpto__info--sup--icon icon icon-tabler icon-tabler-arrows-maximize" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#666" fill="none" stroke-linecap="round" stroke-linejoin="round"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><polyline points="16 4 20 4 20 8" /><line x1="14" y1="10" x2="20" y2="4" /><polyline points="8 20 4 20 4 16" /><line x1="4" y1="20" x2="10" y2="14" /><polyline points="16 20 20 20 20 16" /><line x1="14" y1="14" x2="20" y2="20" /><polyline points="8 4 4 4 4 8" /><line x1="4" y1="4" x2="10" y2="10" /></svg>
                            <p class="dpto__info--sup--text">{{dpto.sup}}</p>
                        </div>
                        <div class="dpto__info--banio icon-text-block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="dpto__info--banio--icon icon icon-tabler icon-tabler-bath" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <path d="M4 12h16a1 1 0 0 1 1 1v3a4 4 0 0 1 -4 4h-10a4 4 0 0 1 -4 -4v-3a1 1 0 0 1 1 -1z" />  <path d="M6 12v-7a2 2 0 0 1 2 -2h3v2.25" />  <path d="M4 21l1 -1.5" />  <path d="M20 21l-1 -1.5" /></svg>
                            <p class="dpto__info--banio--text">{{dpto.banios}}</p>
                        </div>
                    </div>
                    <p class="dpto__info--precio">{{dpto.precio}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import datos from '../dptos.json'
export default {
    data(){
      return{
        infoDptos:[]
      }
    },
    mounted(){
      datos.forEach(dpto => {
        this.infoDptos.push(dpto);
      });
    },
    methods:{
        inmuebleRedirect(id){
            window.location.href = `../inmueble/${id}`;
        }
    }
}
</script>

<style>
.dptos-container{
    /* background-color: red; */
    width: 100%;
    min-height: calc(100vh - 110px);
    margin: 30px auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}
@media (min-width: 768px){
    .dptos-container{
        width: 94%;
    }
}
@media (min-width: 992px){
    .dptos-container{
        width: 90%;
    }
}

.dpto{
    width: 360px;
    height: 340px;
    border: 1px solid #bbb;
    border-radius: 10px;
    margin: 10px 10px 30px 10px;
    background-color: #fff;
}
.dpto:hover{
    cursor: pointer;
    box-shadow: 0px 1px 10px -6px rgba(0,0,0,0.62);
    -webkit-box-shadow: 0px 1px 10px -6px rgba(0,0,0,0.62);
    -moz-box-shadow: 0px 1px 10px -6px rgba(0,0,0,0.62);
}
.dpto__img{
    width: 100%;
    height: 170px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}
.dpto__img .portada-propiedad{
    width: 100%;
    max-height: 100%;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    position: absolute;
}
.vende-alquila{
    position: absolute;
    top: 0;
    left: 0;
    height: 100px;
    width: 100px;
}
.dpto__info{
    width: 100%;
    height: 170px;
    padding: 10px;
}

.dpto__info--precio,
.dpto__info--titulo{
    font-weight: 700;
    font-size: 20px;
    /* text-transform: uppercase; */
}
.dpto__info--ubi{
    margin-top: 7px;
}
.icons-info--container{
    display: flex;
    margin: 7px 0;
}
.icon-text-block{
    display: flex;
    align-items: center;
    height: 20px;
    margin-right: 30px;
}
.dpto__info--sup--icon,
.dpto__info--ubi--icon,
.dpto__info--banio--icon{
    position: relative;
    top: 1px;
    margin-right: 5px;
}
.dpto__info--sup--text,
.dpto__info--banio--text,
.dpto__info--ubi--text{
    color: #666;
    font-weight: bold;
}
.dpto__info--ubicacion{
    font-weight: 700;
}
.dpto__info--precio{
    margin-top: 20px;
}
</style>