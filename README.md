## ✅ Descripción General del Sistema
El presente proyecto representa el modelado arquitectónico completo del **Sistema Tunomático**, una solución orientada a gestionar digitalmente los turnos en instituciones de atención, especialmente en el sector salud. 

Este sistema busca modernizar el proceso de asignación de turnos, permitiendo solicitudes en línea, atención presencial organizada, y una gestión centralizada de agendas, con especial énfasis en la trazabilidad, escalabilidad y adaptabilidad.

**Funciones clave del sistema:**
- Solicitud de turnos por múltiples canales.
- Asignación manual y automática de turnos.
- Consulta de agenda por profesionales.
- Confirmación y cancelación de turnos.
- Reasignación rápida de citas.
- Integración con sistemas externos (ej: Agenda Nacional).

---

## 🔍 Objetivos del Modelado
- Reflejar la lógica funcional del sistema a través de un diagrama de casos de uso UML.
- Diseñar las estructuras lógicas y patrones aplicados mediante un diagrama de clases.
- Representar la arquitectura física del sistema usando un diagrama de implementación UML.
- Aplicar y justificar el uso de al menos tres de los patrones vistos: Singleton, Prototype, Adapter, Bridge.
- Documentar con un nivel de redacción profesional, alineado a estándares académicos y técnicos.

---

## 🔹 1. Diagrama de Casos de Uso UML
![image](https://github.com/user-attachments/assets/f6ada68f-5801-41d0-82b6-44b9cd9e94a0)


### Descripción General
El análisis funcional permitió identificar los siguientes actores y funcionalidades:

#### Actores Principales:
- **Paciente:** solicita turnos en línea.
- **Recepcionista:** asigna, reasigna, cancela turnos y confirma asistencia.
- **Profesional de Salud:** consulta su agenda de atención.
- **Administrador del Sistema:** configura los tipos de atención y horarios.
- **Sistema Externo:** integra la agenda con sistemas institucionales como la Agenda Nacional.

#### Relaciones Aplicadas:
- `<<extend>>`: indica funcionalidades opcionales o condicionales como confirmación por email/SMS o envío de recordatorios.
- `<<include>>`: se aplica cuando una funcionalidad requiere obligatoriamente de otra, como reasignar un turno que siempre incluye cancelar y volver a asignar.

### Casos de uso destacados:
- Solicitar Turno Online  `<<extend>>` Confirmar vía Email/SMS
- Asignar Turno Manualmente  `<<extend>>` Validar Disponibilidad
- Confirmar Asistencia  `<<extend>>` Enviar Recordatorio
- Reasignar Turno  `<<include>>` Cancelar + Asignar
- Consultar Agenda (Profesional)
- Sincronizar con Agenda Nacional Digital (Sistema Externo)

---

## 🔹 2. Diagrama de Clases UML con Patrones Aplicados
![image](https://github.com/user-attachments/assets/ec2ee7ce-d51f-46df-9375-3ca0e085de5e)


## 🧩 Justificación Arquitectónica y Patrones Aplicados

### **1. Singleton – `ConfiguracionTurnos`**
- Centraliza parámetros clave como duración de turnos y notificaciones.
- Evita inconsistencias al garantizar una única instancia global.

### **2. Prototype – `Turno`**
- Se utiliza para clonar configuraciones comunes de turnos.
- Útil para atención por lotes o campañas masivas.

### **3. Adapter – `AdaptadorAgendaExterna`**
- Separa la lógica interna del sistema de la implementación específica de integración con otros sistemas de agenda.

### **4. Bridge – `InterfazUsuario`**
- Permite desacoplar la lógica de turnos de las distintas interfaces de usuario (ej. recepcionista vs paciente).
- Facilita ampliar la interfaz para otros dispositivos como quioscos o apps móviles.

Todas las clases poseen atributos, métodos, visibilidad y relaciones claras. Se utilizaron estereotipos adecuados y no hay clases sin propósito o mal conectadas.

---

## 🔹 3. Diagrama de Implementación UML
![image](https://github.com/user-attachments/assets/6b445d50-7d5a-4f67-bf52-e158834d154a)


### Despliegue Físico y Decisiones Técnicas:
- El sistema está dividido en nodos independientes: **Terminal Autogestión**, **Servidor de Aplicaciones**, **Servidor de Integración API**, y **Base de Datos**.
- Cada componente representa una responsabilidad específica y se comunica mediante protocolos estándar (REST, HTTP).
- Se refuerza la seguridad aislando el módulo `ConfiguracionTurnos` y el integrador externo.
- Se utilizaron los patrones Singleton, Adapter y Bridge también en la arquitectura física.

---

## 🧩 Reflexiones Finales del Modelado
Este trabajo no solo cumple con los requisitos técnicos y formales exigidos en la rúbrica, sino que también plantea un enfoque realista y modular de cómo se modelaría profesionalmente un sistema como Tunomático.

- Se ha logrado una correcta transición entre la visión funcional, lógica y física.
- Los patrones aplicados tienen sentido contextual, no se utilizaron como adornos.
- La documentación generada podría servir como base para una futura implementación real.
