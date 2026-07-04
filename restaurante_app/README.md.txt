# Sistema de Gestión - restaurante_app

**Estudiante:** Anderson Johao Rodriguez Espinosa 
**Asignatura:** Programación Orientada a Objetos - Semana 6  

## Descripción del Sistema
Este sistema es una solución modular en Python diseñada para gestionar los productos disponibles en un restaurante. Permite registrar diferentes categorías de productos (como platillos y bebidas), realizar un control sobre sus propiedades clave y listar de manera organizada el menú interactivo para el usuario.

## Estructura del Proyecto
El proyecto se organiza bajo una arquitectura modular dividida por responsabilidades:
- `modelos/`: Contiene las clases que representan las entidades de datos (`Producto`, `Platillo`, `Bebida`).
- `servicios/`: Contiene la lógica de negocio para administrar las colecciones de objetos (`Restaurante`).
- `main.py`: Punto de entrada principal que inicializa el sistema y ejecuta los flujos de demostración.

## Principios de POO Aplicados

### 1. Herencia
Se estableció una clase general llamada `Producto` (Superclase) que define los atributos base (`nombre`, `precio`, `disponibilidad`). Las clases `Platillo` y `Bebida` actúan como subclases que heredan estas propiedades y comportamientos mediante la instrucción `super()`, añadiendo además sus propios atributos de especialización (`tipo_platillo` y `volumen_ml` respectivamente).

### 2. Encapsulamiento
Para proteger la integridad de los datos financieros, el atributo `precio` dentro de la clase `Producto` se declaró privado utilizando el prefijo de doble guion bajo (`__precio`). El acceso y modificación de esta propiedad externa se realiza estrictamente a través de los métodos públicos `obtener_precio()` y `cambiar_precio()`, donde además se añadió una regla de validación lógica que impide registrar costes negativos o iguales a cero.

### 3. Polimorfismo
El polimorfismo se evidencia en el método `mostrar_informacion()`. Aunque la clase de servicio `Restaurante` itera de manera uniforme sobre una lista genérica de productos, cada objeto en tiempo de ejecución responde de forma dinámica y personalizada mostrando los atributos únicos de su propia categoría (ya sean los mililitros de una bebida o la clasificación del platillo).

## Reflexión sobre la POO en Proyectos Modulares
La implementación de la Programación Orientada a Objetos bajo un diseño modular permite construir software escalable, limpio y altamente mantenible. Al separar las entidades de datos de los servicios que las gestionan, se mitiga el acoplamiento del código, facilitando que futuros cambios en las reglas de negocio (como añadir una nueva categoría de producto o un nuevo canal de ventas) se realicen de forma aislada sin comprometer la estabilidad global de la aplicación.