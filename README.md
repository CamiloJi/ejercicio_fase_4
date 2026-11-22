# Software FJ - Sistema Integral de Gestión de Clientes, Servicios y Reservas

Proyecto colaborativo desarrollado para la **Fase 4 (Componente Práctico)** del curso **Programación (213023)** de la Universidad Nacional Abierta y a Distancia (**UNAD**).

## Descripción del Sistema
Aplicación orientada a objetos desarrollada en Python **sin uso de bases de datos**, diseñada para gestionar clientes, servicios especializados (salas, alquiler de equipos y asesorías) y reservas en memoria, garantizando continuidad operativa mediante manejo avanzado de excepciones y auditoría en archivos de registro (`.log`).

## Arquitectura del Proyecto
* `excepciones.py`: Jerarquía de excepciones personalizadas heredadas de `SoftwareFJError` con códigos de error propios.
* `entidades.py`: Clase abstracta `Entidad` y clase `Cliente` con encapsulación (`@property`) y validaciones mediante expresiones regulares.
* `servicios.py`: Clase abstracta `Servicio` y tres especializaciones (`ReservaSala`, `AlquilerEquipo`, `AsesoriaEspecializada`) aplicando herencia, polimorfismo y sobrecarga mediante parámetros opcionales (`descuento`, `impuesto`).
* `reservas.py`: Clase `Reserva` con ciclo de vida (`PENDIENTE`, `CONFIRMADA`, `CANCELADA`, `FALLIDA`), bloques `try/except/else/finally` y encadenamiento de excepciones (`raise ... from`).
* `gestor.py`: Clase `GestorFJ` encargada de la administración en memoria, ejecución protegida, generación de logs (`logs/software_fj.log`) y reporte financiero.
* `main.py`: Simulación de 19 operaciones completas (válidas e inválidas) que demuestran la estabilidad del sistema ante fallos.

## Requisitos y Ejecución
1. Contar con **Python 3.10** o superior instalado.
2. Clonar el repositorio y ejecutar el archivo principal:
   ```bash
   python main.py
   ```
   
## Autores y Créditos de Colaboración (UNAD - Grupo Colaborativo)
* **Gustavo Adolfo Silva Hios (`tecnisistem84-prog`):** Creación del repositorio base, arquitectura POO y lógica principal del sistema.
* **Camilo Alexander Anacona Jiménez (`CamiloJi`):** Estandarización modular (`.py` según PEP 8), documentación de clases, archivo `.gitignore` y reporte financiero en `GestorFJ`.
* **Kevin Alejandro Olave Arcos (`alejandroolave`):** Documentación detallada de los bloques de prueba y validación en `main.py`.
