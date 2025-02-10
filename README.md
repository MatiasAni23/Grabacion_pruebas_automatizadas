# Grabacion de ventanas con FFmpeg

## Descripción

Esta solución automatiza pruebas en sitios de retail utilizando Selenium y FFmpeg. Durante las pruebas, se graban múltiples ventanas para capturar las acciones realizadas y medir los tiempos de carga.

## Requisitos

 - Python 3.X
 - Google Chrome
 - ChromeDriver
 - FFmpeg (debe estar en el PATH del sistema)
 -  Paquetes de Python:
     - `selenium`
     - `openpyxl`
     - `pygetwindow`
     - `python-dotenv`
     - `unittest`

## Instalación
1. Clonar el repositorio:
   ```bash
   git clone <repositorio>
   cd <directorio>
   ```
2. Instalar dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Configurar variables de entorno en un archivo `.env`:
   ```
   CHROME_DRIVER_PATH=<ruta_del_chromedriver>
   OUTPUT_FOLDER=<ruta_de_salida>
   EMAIL=<tu_email>
   PASSWORD=<tu_password>
   PASSWORD2=<tu_password_alternativa>
   RUT=<tu_rut>
   ```
4. Instalar FFmpeg y agregarlo al PATH:
   - Descarga FFmpeg desde [Windows builds from gyan.dev](https://www.gyan.dev/ffmpeg/builds/).
   - Descarga la versión `ffmpeg-release-essentials.zip`.
   - Extrae los archivos y ubícalos en una carpeta con un nombre referencial en los archivos del sistema.
   - Agrega la ruta del ejecutable `ffmpeg.exe` al PATH del sistema.
   - Verifica la instalación ejecutando `ffmpeg -version` en la terminal.

## Uso
Para ejecutar las pruebas, usa el siguiente comando:
```bash
python Grabacion_ventanas.py
```

## Funcionalidades
- **Ejecución de pruebas automatizadas** en sitios web de retail.
- **Grabación de pantalla** de múltiples ventanas utilizando FFmpeg.
- **Registro de tiempos de carga** en archivos de texto y Excel.
- **Resaltado de elementos** en la grabación para identificar interacciones.

## Estructura del Código
- `Pruebas_retail`: Clase principal con los casos de prueba.
- `setUpClass()`: Configura los navegadores y crea los archivos de reporte.
- `grabar_multiples_ventanas()`: Inicia la grabación de una ventana específica.
- `iniciar_grabacion()`: Ejecuta FFmpeg para grabar la pantalla.
- `detener_grabacion()`: Detiene la grabación de una ventana específica.
- `create_excel_report()`: Genera un archivo de Excel para almacenar los tiempos de carga.
- `log_performance()`: Registra los tiempos de carga de cada acción.
- `test_xx`: Casos de prueba individuales para distintas interacciones en los sitios web.

## Resultados
Los resultados se almacenan en:
- `Reporte_Tiempos_Carga_<fecha>.txt`
- `Reporte_Tiempos_de_Carga.xlsx`
- Carpeta de videos en `<ruta_de_salida>/grabacion_<fecha>`

## Notas
- FFmpeg debe estar instalado y agregado al PATH del sistema.
- Se recomienda ejecutar las pruebas en un entorno con buena conexión a Internet para obtener tiempos de carga precisos.


















