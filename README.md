# Sistema de Gestión de Planilla (Programación 2)

## Descripción del proyecto

Este proyecto consiste en un **sistema de organización de planilla de empleados y patronos**, desarrollado en **Java**, cuyo objetivo principal es **automatizar el cálculo de pagos, rebajos sociales y la generación de reportes en PDF**, además del **envío automático del comprobante por correo electrónico (Gmail)** a cada empleado.

El sistema permite:

* Gestionar empleados (CRUD) y patronos
* Calcular el salario bruto y neto
* Aplicar rebajos sociales del empleado
* Calcular el total que el patrono debe pagar por planilla
* Generar un **PDF detallado de la planilla**
* Enviar el **PDF al correo del empleado** utilizando Gmail

---

##  Funcionalidades principales

* Gestión de empleados (datos personales, salariales y CRUD)
* Cálculo automático de rebajos sociales
* Cálculo del monto total a pagar por el patrono
* Generación de reportes en **PDF**
* Envío de comprobantes de pago por **correo electrónico**
* Uso de librerías externas para PDF y correo

---

##  Estructura y orden del proyecto

El proyecto está organizado de la siguiente manera:

```
Programacion2---Trabajo-U/
│
├── src/
│   ├── main/
│   │   ├── AccesoDatos/
│   │   │   ├── AccesoDatosEmpleados.java //Contiene el CRUD de empleados que se guardan en ListaEmpleados.txt en la raiz del proyecto
│   │   │   ├── CrearEmpleadoPDF.java // Se encarga de crear el PDF para cada empleados respectivamente
│   │   │   ├── CrearPatronoPDF.java// Se encarga de crear el PDF para el patrono
│   │   │   ├── EnviarCorreo.java // Carga la confiSMTP, crear la session, adjuntar el PDF y enviar el correo
│   │   │   ├── IdControl.java //  Se encarga de cargar y agregar los id ya que se guardan los datos en un txt pero este lo que hace es contar el total, lo guarda y cuando  se agrega uno se suma
│   │   ├── Entidades/
│   │   │   ├── Correos.java //Contiene el asunto,  mensajePDF y un mensaje de cuerpo del correo
│   │   │   ├── Deducciones.java // Hereda de Correos y contiene ccss, impuestoRenta, salarioNeto, asociacionSocial
│   │   │   ├── Empleados.java // Contiene nombre, apellido, salarioBruto, contraseña,  id,  verificacion y  un array listaEmpleados
│   │   │   ├── Nominas.java // Hereda de Correos y contiene ccssPatrono, aportesInstitucionales, aportesLPT, totalPagar, pagoPatronoTotal
│   │   ├── Excepciones
│   │   │   ├── CustomException.java // Faltó implementar las excepciones personalizadas
│   │   ├── LogicaNegocio/
│   │   │   ├── LogicaDeducciones.java // Aplica las deducciones de los empleados, agrega los datos a sus correos y agrega los datos al PDF
│   │   │   ├── LogicaEmpleados.java // Aplica el CRUD de lo que se ingresa para mandarlo a Acceso
│   │   │   ├── LogicaNominas.java // Aplica  rebajas del patrono y agrega los datos al PDF y correo
│   │   ├── Presentacion/
│   │   │   ├── App.java
│   │   │   ├── VentanaLogin.java
│   │   ├── Presentacion.EmpleadosVentana/
│   │   │   ├── VentanaCorreosEmpleados.java
│   │   │   ├── VentanaEmpleados.java
│   │   │   ├── VentanaMirarPlantilla.java
│   │   ├── Presentacion.PatronoVentana/
│   │   │   ├── VentanaCorreos.java
│   │   │   ├── VentanaPatrono.java
│   │   │   ├── VentanaPlantilla.java
│   │   ├── Servicios/ (Interfaces)
│   │   │   ├── ServicioDeducciones.java
│   │   │   ├── ServicioEmpleado.java
│   │   │   ├── ServicioIdControl.java
│   │   │   ├── ServicioPatrono.java
│   │   ├── Imagenes/
│
├── config.txt
├── IdControl.txt
├── ListaEmpleados.txt
│
├── lib/
│   ├── itextpdf-5.5.4.jar
│   ├── activation-1.1.jar
│   └── mail.jar
│
├── Reporte Nomina.pdf
├── Reporte Salarial.pdf
│
├── README.md
```
---

## Librerías externas utilizadas

Para el correcto funcionamiento del sistema, se utilizan los siguientes **JAR externos**:

* **iTextPDF 5.5.4**

  * Generación de archivos PDF
* **activation 1.1**

  * Soporte para manejo de datos en correos
* **JavaMail (mail.jar)**

  * Envío de correos electrónicos mediante Gmail

Estas librerías deben agregarse al **Build Path** del proyecto.

---

## Generación del PDF

El sistema genera un PDF que contiene:

* Datos del empleado
* Salario bruto
* Rebajos sociales aplicados
* Salario neto
* Total pagado por el patrono

---

## Envío de correo electrónico

Una vez generado el PDF:

* Se adjunta automáticamente
* Se envía al correo del empleado usando **Gmail**
* Requiere credenciales válidas y configuración SMTP (Que esta configurado en un .txt para cuando se quiera realizar cambios ir a la raiz del proyecto y el archivo "config" para no entrar al codigo para hacer esos cambios)

---

## Como ejecutar el programa

1. Importar el proyecto en el IDE (Recomendado NetBeans)
2. Agregar los JAR externos al proyecto
3. Configurar el correo Gmail en la clase correspondiente
4. Cambiar el correo del patrono para acceder al apartado de patrono
5. Ejecutar la clase `App.java`

---

##  Académico

Proyecto fue desarrollado como parte del curso **Programación 2**, enfocado en:

* Programación orientada a objetos
* Manejo de librerías externas
* Generación de reportes
* Envío de correos electrónicos
* Automatización de procesos administrativos

---

##  Autor

**Kendall Corrales Sánchez**
