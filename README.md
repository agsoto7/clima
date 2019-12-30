let weatherRequestMadrid =  new  XMLHttpRequest ();
let apiURLstringMadrid =  ' https://api.openweathermap.org/data/2.5/weather?id=3117735&units=imperial&APPID=ce1b41bea110dc29a315acc06cc91b63 ' ;
weatherRequestMadrid . abierto ( ' Get ' , apiURLstringMadrid, true );
weatherRequestMadrid . enviar ();
// JSON en variable para trabajar
weatherRequestMadrid . onload  =   function () {
     deje que weatherDataMadrid =  JSON . parse ( weatherRequestMadrid . responseText );
     // Console.log es solo para ver el JSON desde inspeccionar en Google, se debe quitar una vez terminado
     consola . log (weatherDataMadrid);
     // Impresión de la variable deseada (desde JSON)
     documento . getElementById ( ' CurrentWeather-Madrid ' ). innerHTML  =  weatherDataMadrid . principal . temp  +  " ° F " ;
     // Obtención de la imagen desde el servidor usando el JSON
     let iconMadrid =  " http://openweathermap.org/img/w/ "  +  weatherDataMadrid . tiempo [ 0 ]. icono  +  " .png " ;
     deje descMadrid =  weatherDataMadrid . tiempo [ 0 ]. descripción ;
     // Impresión de imagen según el clima actual junto con los atributos src y alt
     documento . getElementById ( ' ImgWeather-Madrid ' ). setAttribute ( ' src ' , iconMadrid);
     documento . getElementById ( ' ImgWeather-Madrid ' ). setAttribute ( ' alt ' , descMadrid);
}
