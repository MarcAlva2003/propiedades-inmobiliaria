<template>
    <div class="inmueble-container">
        <div v-for="inm of infoInm" v-bind:key="inm.id">
            <div class="info-principal">
                <div class="images-slider">
                    <img src="../assets/void.png" alt="void-img" class="void-img">
                    <img class="inm-img" :src="inm.imgs[nroImg]" alt="Imagen propiedad" @click="overlayIsOpen = true">
                    <div class="boton-atras boton-imgs" @click="atras()">
                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-arrow-down-circle" width="32" height="32" viewBox="0 0 24 24" stroke-width="2" stroke="#555" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <circle cx="12" cy="12" r="9" />  <line x1="8" y1="12" x2="12" y2="16" />  <line x1="12" y1="8" x2="12" y2="16" />  <line x1="16" y1="12" x2="12" y2="16" /></svg>
                    </div>
                    <div class="boton-adelante boton-imgs" @click="adelante()">
                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-arrow-up-circle" width="32" height="32" viewBox="0 0 24 24" stroke-width="2" stroke="#555" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <circle cx="12" cy="12" r="9" />  <line x1="12" y1="8" x2="8" y2="12" />  <line x1="12" y1="8" x2="12" y2="16" />  <line x1="16" y1="12" x2="12" y2="8" /></svg>
                    </div>
                    <b class="img-count">{{nroImg+1}}/{{infoInm[0].imgs.length}}</b>
                </div>
                <div class="dpto__info">
                    <p class="dpto__info--titulo">{{inm.titulo}}</p>
                    <div class="dpto__info--ubi icon-text-block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="dpto__info--ubi--icon icon icon-tabler icon-tabler-map-pin" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#666" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <circle cx="12" cy="11" r="3" />  <path d="M17.657 16.657l-4.243 4.243a2 2 0 0 1 -2.827 0l-4.244 -4.243a8 8 0 1 1 11.314 0z" /></svg>
                            <p class="dpto__info--ubi--text">{{inm.ubicacion}}</p>
                        </div>
                    <div class="icons-info--container">
                        
                        <div class="dpto__info--sup icon-text-block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="dpto__info--sup--icon icon icon-tabler icon-tabler-arrows-maximize" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#666" fill="none" stroke-linecap="round" stroke-linejoin="round"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><polyline points="16 4 20 4 20 8" /><line x1="14" y1="10" x2="20" y2="4" /><polyline points="8 20 4 20 4 16" /><line x1="4" y1="20" x2="10" y2="14" /><polyline points="16 20 20 20 20 16" /><line x1="14" y1="14" x2="20" y2="20" /><polyline points="8 4 4 4 4 8" /><line x1="4" y1="4" x2="10" y2="10" /></svg>
                            <p class="dpto__info--sup--text">{{inm.sup}}</p>
                        </div>
                        <div class="dpto__info--banio icon-text-block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="dpto__info--banio--icon icon icon-tabler icon-tabler-bath" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <path d="M4 12h16a1 1 0 0 1 1 1v3a4 4 0 0 1 -4 4h-10a4 4 0 0 1 -4 -4v-3a1 1 0 0 1 1 -1z" />  <path d="M6 12v-7a2 2 0 0 1 2 -2h3v2.25" />  <path d="M4 21l1 -1.5" />  <path d="M20 21l-1 -1.5" /></svg>
                            <p class="dpto__info--banio--text">{{inm.banios}}</p>
                        </div>
                    </div>
                    <p class="dpto__info--precio">{{inm.precio}}</p>
                </div>
            </div>
            <hr style="margin: 50px 5px">
            <div class="info-secundaria">
                <h2>Detalles</h2>
                <ul class="lista-detalles">
                    <li><p>Calle:</p><p>{{inm.calle}}</p></li>
                    <li><p>Altura:</p><p>{{inm.numero}}</p></li>
                    <li><p>Piso:</p><p>{{inm.piso}}</p></li>
                    <li><p>Orientació n:</p><p>{{inm.orientacion}}</p></li>
                    <li><p>Tipo de vivienda:</p><p>{{inm.tipoC}}</p></li>
                    <li><p>Superficie:</p><p>{{inm.sup}}</p></li>
                    <li><p>Ambientes:</p><p>{{inm.ambientes}}</p></li>
                    <li><p>Baños:</p><p>{{inm.banios}}</p></li>
                    <li><p>Dormitorios:</p><p>{{inm.dormitorios}}</p></li>
                    <li><p>Sup. Cubierta:</p><p>{{inm.sup}}</p></li>
                    <li><p>Año de construcción:</p><p>{{inm.aConstruccion}}</p></li>
                </ul>
                <hr>
                <h2>Descripción</h2>
                <p v-for="descInm of inm.desc" v-bind:key="descInm"><br>{{descInm}}</p>
            </div>
            <div v-show="overlayIsOpen" class="overlay-imgs">
                <div class="overlay-close-button" @click="overlayIsOpen = false">
                    <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-x" width="44" height="44" viewBox="0 0 24 24" stroke-width="2" stroke="#ffffff" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <line x1="18" y1="6" x2="6" y2="18" />  <line x1="6" y1="6" x2="18" y2="18" /></svg>
                </div>
                <div class="overlay--images-slider">
                    <img src="../assets/void.png" alt="overlay--void-img" class="void-img">
                    <img class="overlay--inm-img" :src="inm.imgs[nroImg]" alt="Imagen propiedad" @click="overlayIsOpen = false">
                    <div class="boton-atras boton-imgs" @click="atras()">
                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-arrow-down-circle" width="32" height="32" viewBox="0 0 24 24" stroke-width="2" stroke="#555" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <circle cx="12" cy="12" r="9" />  <line x1="8" y1="12" x2="12" y2="16" />  <line x1="12" y1="8" x2="12" y2="16" />  <line x1="16" y1="12" x2="12" y2="16" /></svg>
                    </div>
                    <div class="boton-adelante boton-imgs" @click="adelante()">
                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-arrow-up-circle" width="32" height="32" viewBox="0 0 24 24" stroke-width="2" stroke="#555" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>  <circle cx="12" cy="12" r="9" />  <line x1="12" y1="8" x2="8" y2="12" />  <line x1="12" y1="8" x2="12" y2="16" />  <line x1="16" y1="12" x2="12" y2="8" /></svg>
                    </div>
                    <p class="overlay--img-count">{{nroImg+1}}/{{infoInm[0].imgs.length}}</p>
                </div>
                
            </div>
        </div> 
    </div> 
</template>
<script>
import inmData from '../dptos.json'
export default {
    data(){
        return{
            idInm: this.$route.params.id,
            infoInm:[],
            nroImg: 0,
            overlayIsOpen:false
        }
    },
    mounted(){
      inmData.forEach((dpto) => {
        if(dpto.id == this.idInm){
            this.infoInm.push(dpto);
        }
      });
    },
    methods:{
        atras(){
            if (this.nroImg > 0) {
                this.nroImg = this.nroImg - 1;
            }
        },
        adelante(){
            if(this.nroImg < (this.infoInm[0].imgs.length - 1)){
                this.nroImg = this.nroImg + 1;
            }
        }
    }
}
</script>
<style scoped>
.inmueble-container{
    /* background-color: red; */
    width: 90%;
    margin: 30px auto 30px;
    background-color: rgb(240, 240, 240);
    padding: 10px;
    border-radius: 7px;
}
@media (min-width: 768px){
    .inmueble-container{
        width: 94%;
    }
}
@media (min-width: 768px){
    .inmueble-container{
        width: 90%;
        padding: 20px;
    }
}
@media (min-width: 992px){
    .inmueble-container{
        width: 80%;
        padding: 70px;
    }
    .info-principal{
        width: 100%;
        /* background-color: red; */
        display: flex;
        margin-bottom: 80px;
    }
    .dpto__info{
        padding: 80px 70px;
    }
}
.images-slider{
    /* background-color: red; */
    /* border: 1px solid #dedede; */
    /* background-color: #dedede; */
    width: 100%;
    margin: 0 auto;
    max-width: 400px;
    max-height: 400px;
    position: relative;
}
.images-slider .void-img{
    width: 100%;
    max-width: 400px;
}
.images-slider .inm-img{
    max-width: min(100%, 400px);
    max-height: 400px;
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    margin: auto;
}
.inm-img:hover{
    cursor: zoom-in;
}
.boton-imgs{
    transform: rotate(90deg);
    background-color: rgba(240, 240, 240, 0.445);
    height: 32px;
    width: 32px;
    border-radius: 50%;
    position: absolute;
    margin: auto;
    top: 0;
    bottom: 0; 
}
.overlay-close-button:hover,
.boton-imgs:hover{
    cursor: pointer;
}
.boton-atras{
    left: 5px;
    
}
.boton-adelante{
    right: 5px;
}
.img-count{
    position: absolute;
    right: 0;
    left: 0;
    bottom: 5px;
    margin: auto;
    text-align: center;
}
.dpto__info--titulo{
    font-size: 25px;
    margin-bottom: 15px;
}
.dpto__info--precio{
    font-size: 25px;
    padding-bottom: 10px;
}

.lista-detalles{
    border-radius: 10px;
    width: min(100%, 500px);
    border: 1px solid rgba(73, 73, 73, 0.541);;
    list-style: none;
    padding: 0;
}
.lista-detalles p{
    padding: 10px;
}
.lista-detalles li{
    display: grid;
    grid-template-columns: repeat(2,1fr);
}
.lista-detalles li:nth-child(even){
    background-color: #97c899;
}
.lista-detalles li:nth-child(odd){
    background-color: #97c89980;
}
.lista-detalles li:first-child{
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}
.lista-detalles li:last-child{
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
}

.overlay-imgs{
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, .9);
    display: flex;
    justify-content: center;
    align-items: center;
}
.overlay--images-slider{
    width: 100%;
    margin: 0 auto;
    max-width: 700px;
    max-height: 700px;
    position: relative;
}
.overlay--inm-img{
    max-width: min(100%, 700px);
    max-height: 700px;
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    margin: auto;
}
.overlay--inm-img:hover{
    cursor: zoom-out;
}
.overlay--img-count{
    position: absolute;
    right: 0;
    left: 0;
    bottom: 5px;
    margin: auto;
    text-align: center;
    width: 40px;
    border-radius: 20px;
    color: #fff;
    background-color: rgba(0, 0, 0, 0.356);
    padding: 3px;
}
.overlay-close-button{
    position: fixed;
    top: 10px;
    right: 10px;
}
</style>