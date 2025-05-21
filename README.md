# Dise-o-de-Diagramas-de-Implementaci-n-con-Patrones-de-Dise-o

## 🐾 Descripción General del Sistema

El "Sistema de Cuidado de Gato Inteligente" tiene como objetivo automatizar las tareas de cuidado de una mascota felina dentro de un entorno doméstico. Este sistema permite al dueño del gato interactuar con dispositivos inteligentes para alimentar al animal, preparar comida adecuada, proporcionarle juguetes clonados y permitirle jugar en diferentes superficies.

El sistema está construido aplicando patrones de diseño orientados a objetos, lo que permite modularidad, mantenibilidad y escalabilidad.


## Diagrama de Casos de Uso

### ✏️ Explicación de Relaciones

- `<<include>>`: representa acciones internas necesarias que siempre se ejecutan como parte del caso principal.
  - Ej: "Solicitar comida" incluye "Activar comedero automático".
- `<<extend>>`: representa comportamientos opcionales que se ejecutan solo bajo ciertas condiciones.
  - Ej: "Jugar con el gato" puede extenderse a "Usar juguete en piso" o "Usar juguete en rascador".


![image](https://github.com/user-attachments/assets/00fd9c4d-f8c8-4de6-bdbc-194e662d0ccc)


##Diagrama de Clases UML

### 🧠 Justificación de Patrones

- `<<Singleton>> Comedero`: garantiza una única instancia del dispensador de comida en toda la casa.
- `<<Prototype>> JugueteGato`: permite clonar juguetes personalizados para el gato.
- `<<Adapter>> AdaptadorComidaGato`: transforma platos humanos en comida apta para felinos.
- `<<Bridge>> Juguete`: abstrae la interacción con las superficies físicas `Piso` y `Rascador`.


![image](https://github.com/user-attachments/assets/65b023ee-30fc-4820-9062-9c810f2a5491)

##Diagrama de Implementación

### 🧱 Explicación de Decisiones Técnicas

- **Casa**: nodo físico donde se encuentran el comedero automático y el juguete del gato.
- **Cocina**: módulo encargado de la adaptación de alimentos, separado del resto por lógica funcional.
- **Tienda de Mascotas**: módulo externo o remoto encargado de la clonación de juguetes mediante el patrón Prototype.

Cada componente representa un subsistema desplegable físicamente o de forma virtual, asegurando escalabilidad y separación de responsabilidades.


![image](https://github.com/user-attachments/assets/ae17f82b-1988-407b-af0b-9813f956fe84)


## 📌 Reflexiones Finales del Modelado

Este modelado permitió aplicar patrones de diseño en un contexto doméstico realista y didáctico. El uso de `Singleton`, `Prototype`, `Adapter` y `Bridge` permitió diseñar un sistema flexible, modular y fácil de mantener. Los diagramas muestran la transición desde el modelo lógico (clases y casos de uso) hasta el despliegue físico del sistema (nodos y componentes).

Este ejercicio refuerza la importancia de pensar en la escalabilidad, modularidad y claridad en la arquitectura desde las primeras fases del diseño de software.
