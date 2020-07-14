<template>
    <div class="jumbotron" id="app">
        <h1 class="titulo">La lista de {{name}}!</h1>
        <div class="card">
            <h4 class="titulo_cuadro card-title">Actividades realizadas por {{name}}</h4>
            <ul>
                <li class="texto_consulta" v-for ="(actividad, posicion) in actividades" v-bind:key="posicion">{{actividad}}</li>
            </ul>
        </div>
        <div class="card">
            <h4 class="titulo_cuadro" v-if="cuarentena == true">Actividades que {{name}} hará post-cuarentena</h4>
            <h4 class="titulo_cuadro" v-else>Actividades que {{name}} hará ahora</h4>
            <ul>
                <li class="texto_consulta" v-for ="(pendientes, posicion) in por_hacer"  v-bind:key="posicion">{{pendientes}}</li>
            </ul>
        </div>
    </div>
</template>
<script>

export default({
    name:"MiLista",
    el: "#app",
    data: function() {
        return {
            name: "Josh",
            cuarentena: true,
            actividades: [
                "Terminar la U",
                "Viajar",
                "Grabar música",
                "Crear contenido",
                "Emprender"
            ],
            por_hacer: [
                "Acampar",
                "Más viajes",
                "Construir una app para jugar",
                "Salir a comer chatarra"
            ]
        }
    }
})
</script>
<style scoped>
    .jumbotron{
        background: url(https://giffiles.alphacoders.com/208/208893.gif ) repeat  center;
        background-size: 100% ;
        height: 45rem;
    }

    .titulo{
        font-weight: bold;
        padding: 20px;
        color:white;
        font-size: 4rem;
        text-decoration: underline;
    }

    .titulo_cuadro, .texto_consulta{
        font-weight: bold;
        font-size: 1.5rem;
        text-align: justify;
    }
    .card{
        color:white;
        display: inline-block;
        background-color: black;
        opacity: .8;;
        width: 25rem;
        border-radius: 20px;
        border: white 5px solid;
        padding: 2rem;
        margin: 5rem;
        transition: transform .2s;
    }
        .card:hover{
        color:black;
        display: inline-block;
        background-color: white;
        opacity: .8;;
        width: 25rem;
        border-radius: 20px;
        border: black 5px solid;
        padding: 2rem;
        margin: 5rem;
        transform: scale(1.2);
    }

</style>