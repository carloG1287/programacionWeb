<!DOCTYPE html>
<html>
  <head>
    <title>Datos de los empleados</title>
  </head>
  <body>
    <?php
      $totalEmpleadosFemeninos = 0;
      $totalHombresCasados = 0;
      $totalMujeresViudas = 0;
      $totalEdadHombres = 0;
      $numeroHombres = 0;

      if (isset($_POST['submit'])) {
        for ($i = 0; $i < 5; $i++) {
          $nombreApellido = $_POST['nombreApellido'][$i];
          $edad = $_POST['edad'][$i];
          $estadoCivil = $_POST['estadoCivil'][$i];
          $sexo = $_POST['sexo'][$i];
          $sueldo = $_POST['sueldo'][$i];

          if ($sexo == "F") {
            $totalEmpleadosFemeninos++;

            if ($estadoCivil == "V" && $sueldo == 3) {
              $totalMujeresViudas++;
            }
          } else {
            $numeroHombres++;
            $totalEdadHombres += $edad;

            if ($estadoCivil == "C" && $sueldo == 3) {
              $totalHombresCasados++;
            }
          }
        }
      }
    ?>

    <form action="index.php" method="post">
      <?php for ($i = 0; $i < 5; $i++) { ?>
        <h3>Empleado <?php echo $i + 1; ?></h3>
        <p>
          <label for="nombreApellido">Nombre y apellido:</label>
          <input type="text" name="nombreApellido[]" id="nombreApellido">
        </p>
        <p>
          <label for="edad">Edad:</label>
          <input type="number" name="edad[]" id="edad">
        </p>
        <p>
          <label for="estadoCivil">Estado civil:</label>
          <select name="estadoCivil[]" id="estadoCivil">
            <option value="S">Soltero</option>
            <option value="C">Casado</option>
            <option value="V">Viudo</option>
          </select>
        </p>
        <p>
          <label for="sexo">Sexo:</label>
          <select name="sexo[]" id="sexo">
            <option value="F">Femenino</option>
            <option value="M">Masculino</option>
          </select>
        </p>
        <p>
          <label for="sueldo">Sueldo:</label>
<select name="sueldo[]" id="sueldo">
            <option value="1">Menos de 1000 Bs.</option>
            <option value="2">Entre 1000 y 2500 Bs.</option>
            <option value="3">Mas de 2500 Bs.</option>
          </select>
        </p>
      <?php } ?>
      <input type="submit" name="submit" value="Enviar">
    </form>
<?php if (isset($_POST['submit'])) { ?>
  <h2>Resultados</h2>
  <p>Total de empleados del sexo femenino: <?php echo $totalEmpleadosFemeninos; ?></p>
  <p>Total de hombres casados que ganan más de 2500 Bs.: <?php echo $totalHombresCasados; ?></p>
  <p>Total de mujeres viudas que ganan más de 1000 Bs.: <?php echo $totalMujeresViudas; ?></p>
  <p>Edad promedio de los hombres: <?php echo $totalEdadHombres / $numeroHombres; ?></p>
<?php } ?>
