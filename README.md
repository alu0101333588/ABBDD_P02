# ABBDD_P02
Práctica 02 - Administración de Bases de Datos
Realizada por Andrés Hernández Ortega y Luka Kravarusic Sljapic

Proyecto draw.io: https://drive.google.com/file/d/17MgRfRyU7QS2GPIPZw6tTKoTyzIJD5LS/view?usp=sharing
# Modelo entidad-relación
![Modelo entidad-relación](/Viveros.drawio.png "ER Model")


# Entidades definidas
## Vivero

* Un vivero posee un NOMBRE
* Contiene un identificador ID único
* Se encuentra ubicado en una LATITUD y LONGITUD
* **Identificador**: ‘Id’

### Ejemplo
* NOMBRE: Jardines Madre del Agua
* ID: 00025
* MUNICIPIO: San Cristóbal de La Laguna
* PROVINCIA: Santa Cruz de Tenerife
* LATITUD: 28.504121328130214
* LONGITUD: -16.308638413644754


## Zona
* Cada zona tiene un NOMBRE único
* Cada zona se encuentra en una LATITUD y LONGITUD
* Cada zona tiene un TIPO asociado
* Cada zona tiene un atributo calculado PRODUCTIVIDAD que se calcula en base al atributo PRODUCTIVIDAD de la entidad EMPLEADO
* **Identificador**: NOMBRE

### Ejemplo
* ID: 0040
* NOMBRE: Zona A
* LATITUD: 28.504121328130214
* LONGITUD: -16.308638413644754
* TIPO: Zona exterior
* PRODUCTIVIDAD: 75%
 
## Empleado
* Los empleados cuentan con un identificador ID único
* Tienen un NOMBRE
* Poseen unos APELLIDOS (atributo compuesto):
    * PRIMER APELLIDO
	* SEGUNDO APELLIDO
* Se cuentan con un índice de PRODUCTIVIDAD de la zona (atributo calculado), en función de las ventas que realiza el empleado (pedidos que gestione)
* **Identificador**:  ‘Id’
 
### Ejemplo
* ID: 00356
* NOMBRE: Rofoldo
* APELLIDOS:
	* PRIMER APELLIDO: Izquierdo
	* SEGUNDO APELLIDO: Rodríguez
* PRODUCTIVIDAD: 42,5%

## Producto
* Cada producto tiene un ID único
* Cada producto tiene un NOMBRE
* Cada producto es de un TIPO
* Cada producto está catalogado a un PRECIO
* **Identificador**: ID

### Ejemplo
- ID: 100078
- NOMBRE: Orquídea
- TIPO: Planta
- PRECIO: 45€

## Pedido
* Cada pedido tiene un NUMERO PEDIDO
* Cada pedido tiene una FECHA en la que se ha realizado
* **Identificador**: NUMERO PEDIDO

### Ejemplo
* NUMERO PEDIDO: 10050
* FECHA: ‘10-10-2024’

## Cliente Tajinaste Plus
* Un cliente cuenta con un identificador ID único
* Posee un NOMBRE
* Cuenta con unos APELLIDOS (atributo compuesto):
	* PRIMER APELLIDO
	* SEGUNDO APELLIDO
* Según la fecha en la que se haya dado de alta en el programa cuenta con una FECHA DE INGRESO
* Los clientes cuentan con una BONIFICACIÓN en función del número de compras que realicen
* **Identificador**: ID

### Ejemplo
* ID: 0035
* NOMBRE: Luka
* APELLIDOS:
	* PRIMER APELLIDO: Modric
	* SEGUNDO APELLIDO: Santana
* BONIFICACIONES: 2,25%
* FECHA DE INGRESO: 10/10/2023


# Relaciones entre entidades
## Vivero-zona
* Un vivero puede tener una o varias zonas.
* Una zona puede estar en un vivero.

## Zona-Empleado
* En una zona puede trabajar uno o varios empleados, pero sólo en una única epoca del año, clasificada en Invierno, Primavera, Verano y Otoño.
* Un empleado puede trabajar en una o varias zonas, en una única epoca del año.


## Zona-Producto
* Una zona puede no tener ningún producto o puede tener varios productos, con una cantidad del mismo establecida en la relación.
* Un producto puede estar en una zona o en varias zonas, con una cantidad establecida en la relación.


## Producto-Pedido
* Un producto puede no estar contenido en ningún pedido o en varios pedidos. La cantidad del mismo se establece en la relación
* Un pedido puede contener un producto o varios productos, con la cantidad en la relación.


## Empleado-Pedido
* Un empleado puede gestionar uno o varios pedidos
* Un pedido puede ser gestionado por un empleado.


## Pedido-Cliente Tajinaste Plus
* Un pedido puede no ser realizado por ningún Cliente de Tajinaste Plus o puede ser realizado por un Cliente de Tajinaste Plus.
* Un cliente de Tajinaste Plus puede no realizar ningún pedido o puede hacer varios pedidos.
