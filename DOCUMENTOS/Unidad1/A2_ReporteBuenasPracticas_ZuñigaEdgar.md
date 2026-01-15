# Actividad 2 — Reporte de Buenas Prácticas y Documentación de Código

**Alumno:** Zuñiga Lugo Edgar Daniel
**Grupo:** 2IRD-G1
**Fecha:** 14 de Enero de 2026
**Unidad:** 1

## 1. Objetivo del reporte
- Analizar y comprender la importancia de las normas de codificación para el desarrollo de software mantenible en Java y Python.
- Aplicar estándares de documentación técnica para mejorar la legibilidad y colaboración en proyectos de programación estructurada.

## 2. Buenas prácticas de codificación
### 2.1 Nombres de variables
- **Reglas:**
  - **Descriptividad:** Los nombres deben indicar claramente qué almacena la variable (ej. `precioTotal` en lugar de `p`).
  - **Convención Java:** Se utiliza *camelCase* (ej. `numeroDeCuenta`).
  - **Convención Python:** Se utiliza *snake_case* según PEP 8 (ej. `numero_de_cuenta`).
- **Ejemplo:** Evitar `int x = 5;` y preferir `int diasSemana = 5;`.

### 2.2 Comentarios
- **Cuándo comentar:** Se debe comentar el "por qué" de una lógica compleja, no el "qué" hace el código (el código debe explicarse solo). También es vital en cabeceras de funciones.
- **Qué evitar:** Comentarios obvios o redundantes como `i++; // Incrementa i` o código comentado que ya no sirve (código muerto).

### 2.3 Estructura del código
- **Indentación:** Es crucial para la jerarquía visual. En Python es obligatoria (4 espacios estándar). En Java mejora la lectura de bloques `{}`.
- **Modularidad:** Dividir problemas grandes en funciones pequeñas que realicen una sola tarea (Principio de Responsabilidad Única).
- **Evitar duplicidad:** Principio DRY (Don't Repeat Yourself). Si copias y pegas código, mejor crea una función.

## 3. Documentación del código
### 3.1 Estándares
- **Estándar elegido:** JavaDoc para Java y Docstrings (PEP 257) para Python.
- **Elementos recomendados:** Descripción de la función, lista de parámetros (`@param`), tipo de retorno (`@return`) y posibles errores (`@throws`).

### 3.2 Herramientas / enfoque
- **Herramientas:** El uso de generadores automáticos como la herramienta `javadoc` en JDK o extensiones en VS Code como "AutoDocstring".
- **Ventajas:** Permite generar sitios web de documentación (HTML) automáticamente y ayuda a otros desarrolladores a usar nuestras funciones sin leer todo el código interno.

## 4. Ejemplos prácticos

### 4.1 Antes / Después (Ejemplo 1: Nombres y Variables)
**Antes:**
```python
# Código confuso en Python
x = 10
y = 20
def c(a, b):
    return a * b
print(c(x,y))
```
**Después:**
```python
precio_unitario = 10
cantidad_articulos = 20

def calcular_total(precio, cantidad):
    """Calcula el costo total basado en precio y cantidad."""
    return precio * cantidad

total_compra = calcular_total(precio_unitario, cantidad_articulos)
print(total_compra)
```


### 4.2 Antes / Después (Ejemplo 2: Indentación y Estructura en Java)
**Antes:**
```JAVA
public class Main{public static void main(String[] args){
for(int i=0;i<10;i++){System.out.println(i);}}}
```
**Después:**
```JAVA
public class Main {
    public static void main(String[] args) {
        // Correcta indentación para visualizar la jerarquía del bucle
        for (int i = 0; i < 10; i++) {
            System.out.println("Contador actual: " + i);
        }
    }
}
```