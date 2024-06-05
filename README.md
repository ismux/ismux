<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap');

body {
  background: rgb(20,20,20);
}
#container {
  background: rgb(20,20,20);
  overflow: hidden;
  font-family: 'Roboto';
  position: relative;
  margin: 0 0 0 0;
}
#container::after {
  content: '';
  top: 0;
  width: 100%;
  height: 50%;
  background: linear-gradient(180deg, rgba(20,20,20,1) 40%, rgba(20,20,20,0) 100%);
}
#txtContainer {
  display: flex;
  height: 100%;
  width: 80%;
  margin: 0 auto;
  perspective: 450px;
  z-index: 2;
}
#txtWrapper {
  color: #eebc09;
  font-size: 3vw;
  line-height: 1.5em;
  padding: 50px;
  position: absolute;
  width: 80%;
  margin: 0 auto;
  transform-style: preserve-3d;
  transform: rotateX(20deg);
  animation: scroll 50s linear forwards infinite;
}
h1,h2 {
  text-align: center;
  background: rgb(20,20,20);
}
p {
  text-align: left;
  background: rgb(20,20,20);
}
#starContainer {
  z-index: 1;
}
.star {
  display: block;
  height: 3px;
  width: 2px;
  background-color: whitesmoke;
  border-radius: 50%;
  position: absolute;
}
@keyframes scroll {
	from { top: 50%; transform: translateZ(0) rotateX(35deg); }
	to { top: -4500px; transform: translateZ(-2500px) rotateX(36deg); }
}
</style>
<body>
  <div id ="container">
    <div id="starContainer"></div>
    <div id="txtContainer">
      <div id="txtWrapper"></div>
    </div>
  </div>
</body>

<script type="text/javascript">

const textArray = [ { type: "h1", text: "Ismael Plantón" },
                    { type: "h2", text: "Desarrollador web" },
                    { type: "p", text: "Trabajo como desarrollador web desde 2013." },
                    { type: "p", text: "Especializado en tecnologías .Net con C#, he participado en proyectos realizados mediante .Net Framework, pasando por .Net Core hasta .Net 8." },
                    { type: "p", text: "He realizado proyectos implementando architecturas MVC mediante el patrón DDD(Domain Drive Design) y CQRS." },
                    { type: "p", text: "También cuento con conocimientos en JQuery y React con Typescript, manejo del estado mediante Hooks personalizados y Redux." },
                    { type: "p", text: "Manejo de diversas librerías de Front como Boostrap y Material UI." },
                    { type: "p", text: "Conocimientos en el motor de Base de Datos SQL Server." },
                    { type: "p", text: "Autodidacta, siempre a la búsqueda de nuevos retos que afrontar y en constante aprendizaje." },
                    { type: "p", text: "Con la mayor frecuencia posible, subiré diferentes proyectos a modo de piloto que resuelvan alguna funcionalidad concreta usando diversas tecnologías..." } ];


for (var key in textArray) {
    var obj = textArray[key];
    document.getElementById("txtWrapper").innerHTML += "<"+ obj.type +">"+ obj.text +"</"+ obj.type +">";
}

const getRandomNumber = (min, max) => {
  return Math.floor(Math.random() * (max - min) + min);
}

for (var i = 0; i < 200; i++) { 
    var randLeft = getRandomNumber(1, 100);
    var randTop = getRandomNumber(1, 100);
    document.getElementById("starContainer").innerHTML += '<span class="star" style="left:'+ randLeft +'%; top:'+ randTop +'%;"></span>';
}

</script>
