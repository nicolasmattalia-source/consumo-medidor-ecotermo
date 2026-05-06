# Medidor de gas Ecotermo

Aplicacion web para calcular el consumo de un medidor de gas a partir del
tiempo que tarda en consumir 100 dm3.

La herramienta permite seleccionar un medidor, ingresar minutos y segundos, y
obtener automaticamente el consumo en dm3/h, el consumo en m3/h, el factor de
correccion y la potencia estimada en kcal/h.

## Funcionalidades

- Calculo de consumo en dm3/h y m3/h.
- Calculo de potencia estimada usando el poder calorifico configurado.
- Busqueda del factor de correccion mas cercano segun la tabla del medidor.
- Panel lateral de configuracion.
- Alta, edicion y eliminacion de medidores.
- Carga de tablas de correccion desde archivos CSV.
- Guardado de medidores y configuracion general en Firebase Firestore.
- Interfaz responsive para escritorio y celular.
- Accesos rapidos a otros ensayos relacionados.

## Tecnologias

- HTML
- CSS
- JavaScript
- Firebase Firestore
- GitHub Pages

## Archivos principales

- `index.html`: aplicacion completa, estilos, interfaz y logica.
- `ecotermo.png`: logo usado por la app.
- `package.json`: configuracion basica para levantar un servidor local.

## Como usar la aplicacion

1. Abrir la aplicacion en el navegador.
2. Seleccionar el medidor a utilizar.
3. Ingresar los minutos y segundos medidos para el consumo de 100 dm3.
4. Revisar los resultados calculados:
   - Consumo dm3/h
   - Consumo m3/h
   - Factor de correccion
   - Potencia estimada

## Panel de configuracion

El boton de menu abre el panel lateral de configuracion. Desde ahi se pueden
administrar los medidores guardados y editar el poder calorifico del gas.

Las acciones de edicion solicitan una contrasena antes de modificar datos.

## Formato del archivo CSV

Para cargar una tabla de correccion, el archivo debe tener una primera fila de
encabezado y luego filas con caudal y error.

Ejemplo:

```csv
caudal,error
0.5,1.2
1.0,0.8
1.5,-0.3
```

Tambien se aceptan archivos separados por punto y coma:

```csv
caudal;error
0,5;1,2
1,0;0,8
1,5;-0,3
```

## Ejecutar localmente

Instalar las dependencias:

```bash
npm install
```

Iniciar el servidor local:

```bash
npm start
```

El navegador abrira `index.html` automaticamente.

## Despliegue

El proyecto esta pensado para publicarse como sitio estatico en GitHub Pages.
Al estar toda la app contenida en `index.html`, solo es necesario subir los
archivos del proyecto al repositorio y habilitar GitHub Pages desde la rama
principal.

## Base de datos

La aplicacion usa Firebase Firestore para guardar:

- `medidores`: datos de cada medidor, instrumento, unidad y tabla de correccion.
- `configuracion/general`: poder calorifico usado para estimar la potencia.

## Notas

La configuracion de Firebase se encuentra dentro de `index.html`. Si se cambia
de proyecto Firebase, se deben actualizar los valores de `firebaseConfig`.
