<!DOCTYPE html>
<html>
<head>
  <title>Mostly Fluid</title>
  <meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
  
    <script src="http://code.jquery.com/jquery-latest.js"></script>
    <script type="text/javascript">

    <style>
    body { background-image: url(https://cdn.wallpapersafari.com/41/9/h0k9zK.jpg);
background-repeat: no-repeat;
background-attachment: fixed;
background-size: cover;
}

h1{color: rgb(51, 133, 198);}

table { margin: 0 auto;
color: yellow;}

table td{text-align: center;
  padding: 10px;
}
h3{margin: 2px, auto;}



table td:hover{
  background: RGBA(51, 133, 198, 0.5);
  cursor: pointer;
}
button:hover{ cursor:pointer;
  text-decoration:underline;
  color:#00f;}



.container {
  margin: auto;
  display: -webkit-flex;
  display: flex;
  -webkit-flex-flow: row wrap;
  flex-flow: row wrap;
  padding: 5px;
  background: rgba(5, 15, 15, 0.5);
  color: yellow;
}
.columna1,
.columna2,
.columna3,
.columna4{
  width: 300%;
  color: #FF8000;
  border: 2px solid #f2f2f2;
  margin: 2px auto;
}
footer {
		margin:10px;
		text-align:center;
		clear:both;
    color: yellow;
  }
@media (min-width: 800px) {
  .columna2,
  .columna3,
  .columna4 {
    width: 40%;
  }
}
@media (min-width: 1080px) {
  .columna1 { width: 98%; }
  .columna2 { width: 31%; }
  .columna3,
  .columna4 {
    width: 31%;
  }
  .container {
    width: 1080px;
    margin-left: auto;
    margin-right: auto;
    color: yellow;
  }
}
</style>
    $(document).ready(function(){
        /**
         * Funcion para añadir una nueva columna en la tabla
         */
        $("#add").click(function(){
            // Obtenemos el numero de filas (td) que tiene la primera columna
            // (tr) del id "tabla"
            var tds=$("#tabla tr:first td").length;

            // Obtenemos el total de columnas (tr) del id "tabla"
            var trs=$("#tabla tr").length;
            var nuevaFila="<tr>";
            for(var i=0;i<tds;i++){
                // añadimos las columnas
                nuevaFila+="<td>  </td>";
            }
            // Añadimos una columna con el numero de fila correspondiente.
            // ""+(i+1)+"Añadimos uno al total, ya que cuando cargamos los valores para la
            // columna, todavia no esta añadida
            nuevaFila+="<td>"+(trs+1)+" fila";
            nuevaFila+="</tr>";
            $("#tabla").append(nuevaFila);
        });

        /**
         * Funcion para eliminar la ultima columna de la tabla.
         * Si unicamente queda una columna, esta no sera eliminada
         */
        $("#del").click(function(){
            // Obtenemos el total de columnas (tr) del id "tabla"
            var trs=$("#tabla tr").length;
            if(trs>1)
            {
                // Eliminamos la ultima columna
                $("#tabla tr:last").remove();
            }
        });
    });
    </script>


</head>

<body>
  <header>
  <h1>Ejercicio jquerydsdsd</h1>
  </header>

  <div class="container">

  <section class="columna1"><h3>Ejercicio jquery añadir & quitar filas</h3>
    <br>
    <button id="add">+</button>
    <button id="del">-</button>
    <table id="tabla" border=1>
        <tr>
            <td>PRIMER COLUMNA</td>
            <td>SEGUNDA COLUMNA</td>
            <td>TERCER COLUMNA</td>
            <td>CUARTA COLUMNA</td>
            <td>QUINTA COLUMNA</td>
            <td>SEXTA COLUMNA</td>
            <td>SEPTIMA COLUMNA</td>
            <!-- podemos añadir tantas columnas como deseemos -->
            <!--<td>tercera columna</td>-->
        </tr>
    </table>
  </p></section>

  <section class="columna2"><h3>El diseño web fluido o diseño web líquido</h3>
    <br>fluid web design o liquid web design, es aquel que tiende a ocupar todo el ancho de la pantalla, sea cual sea el tamaño de esta. Es un tipo de diseño menos utilizado que el anterior, ya que requiere de mucho más trabajo por parte del diseñador web y a que si no se realiza correctamente su resultado puede resultar bastante atractivo para tamaños de pantalla “normales” y pequeñas, pero cuando se emplean pantallas de muchas pulgadas su estética resulta, cuanto menos, horrible, a no ser que se utilicen técnicas como el uso de max-width para limitar el máximo ancho aceptado por nuestro diseño. En este caso el diseñador web utiliza porcentajes en lugar de píxeles para establecer los anchos de sus diseños, aunque también se pueden emplear píxeles y medidas máximas y mínimas con min-width y max-width. Por suerte es un tipo diseño que cada vez va tomando más terreno y va sustituyendo al diseño fijo.
  </p></section>

    <section class="columna3"><h3>El diseño web elástico</h3>
			<br>Elastic web design, es un tipo de diseño muy parecido al fluido, sólo que en este caso el contenido también crece junto al ancho del diseño para rellenar la pantalla. Es, con diferencia, un tipo de diseño prácticamente residual y muy poco usable. Volvemos a lo mismo que en el caso del diseño fluido, el diseño elástico puede resultar más o menos agradable en tamaños de pantalla más o menos pequeños, pero cuando se utilizan pantallas muy grandes el contenido se vuelve exageradamente irracional, por lo que salvo contadas excepciones, no tiene ningún tipo de razón de ser. En este caso el diseñador web utiliza em para fijar los anchos de su diseño web y del resto del contenido que alberga. Es un tipo de diseño del que debemos alejarnos lo más posible.
		</p></section>

    <section class="columna4"><h3>El diseño web sensible</h3>
			<br>Responsive web design en inglés, es un tipo de diseño que se transforma en función del tipo de dispositivo o del ancho del navegador web que lo visualiza. De esta forma se muestra un diseño web en dispositivos smartphones, otro diferente en dispositivos tipo tabletas, y otro distinto en ordenadores. De esta forma el diseñador web se asegura de que el contenido que visualizan los usuarios se ajusta a las necesidades de su dispositivo y, aunque la información mostrada es exactamente igual, sea cual sea el dispositivo que la visualiza, el diseño varía sensiblemente para optimizar al máximo el acceso a la misma. En este caso el diseñador web emplea diferentes hojas de estilo que cargará mediante el uso de JavaScript en función de las necesidades que se establezcan, principalmente ancho del navegador web y tipo de dispositivo. Este es el diseño que más en auge está teniendo gracias al uso masivo de dispositivos smartphones y tabletas en el uso diario de la Internet. El único problema que plantea este tipo de diseño, además de su complejidad, peso y tráfico generado, es el de la accesibilidad para dispositivos que tienen inhabilitado o que no disponen de tecnología JavaScript, aunque por suerte son una inmensa mayoría en la fauna de Internet.
    </div>
</body>
</html>
