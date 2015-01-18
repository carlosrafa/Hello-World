<!---# Hello-World-->
<!---My first repository-->
<?php
include "config.php";
session_start(); //sempre session_start antes de usar sessions
?>
<!---inicio del programa-->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<!---LLama los estilos AJAX, CSS (JQM)-->
<meta name="viewport" content="width=device-width, initial-scale=1"> 
<link rel="stylesheet" href="jqm/jquery.mobile-1.4.5.min.css" />
<script src="jqm/jquery-1.11.2.min.js"></script>
<script src="jqm/jquery.mobile-1.4.5.min.js"></script>
<link rel="stylesheet" href="receta.css" />
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"/>
<title>Recetario Virtual</title>
</head>
<body>
<div data-role="page"> <!---CONTENEDOR DE LA PAGINA-->
	<div id="logorecetario">
	</div> 
	<div data-role="header" data-position="fixed" data-id="cabeza"> <!---Cabecera-->
	<div data-role="navbar"> <!---MENU-->
	<ul>
	<li><a href="index.php" data-icon="home">INICIO</a></li>
	<li><a href="recetario.php" data-icon="grid">RECETARIOS</a></li>
	<li><a href="sobre.php" data-icon="search">CONTACTENOS</a></li>
	<?php if(isset($_SESSION['cliente'])){	echo "<li><a href='logout.php' target='_self' data-icon='arrow-r'>SALIR</a></li>";
	}
	else { echo "<li><a href='login.php' target='_self' data-icon='arrow-l'>LOGIN</a></li>";}?>
	</li>
	</ul>
	</div> <!---Fin Menu-->
	</div> <!---Fin Cabecera-->
	<div data-role="content"> <!---Contenido-->
	<ul data-role="listview" data-inset="true" >
	<?php if(isset($_SESSION['cliente'])){
	echo "<li>Usuario: <i>".$_SESSION['cliente']."</i></li>";}
	?>
	<li><a href='recetario.php'><center> <h4>VER RECETARIOS</h4></center></a></li>
	<?php 
	if(isset($_SESSION['cliente'])){
		}
	else {
		echo '<li><a href="registro.php">Registrarse</a></li>';
		echo '<li><a href="login.php">Ingresar / Login</a></li>';
		echo "<li>Sin Acceso</li>";
	}
	?>
	</ul>
	</div> <!---Fin Contenido-->
	<div data-role="footer" data-position="fixed" data-id="pie"><!-- pie -->
		<div data-role="navbar"> 
		<ul>
			<li><a href="index.php" data-icon="home"></a></li>
			<li><a href="recetario.php" data-icon="grid"></a></li>
			<li><a href="sobre.php" data-icon="search"></a></li>
			<?php if(isset($_SESSION['cliente'])){	echo "<li><a href='logout.php' target='_self' data-icon='arrow-r'></a></li>";
				}
				else { echo "<li><a href='login.php' target='_self' data-icon='arrow-l'></a></li>";}?>
			</ul>
		</div> 	<!-- Bar -->
	</div>	<!-- fin pie -->
</div> <!---fin pagina-->
</body>
</html>
