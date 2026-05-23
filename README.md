# 🚚 Machine Learning II: Planificación Automática para Almacén Autónomo

Sistema inteligente de planificación automática para la gestión de un almacén robotizado autónomo. Implementa un planificador basado en PDDL (Planning Domain Definition Language) que optimiza el transporte de cajas entre zonas de almacenamiento, demostrando aplicaciones prácticas de IA en logística.

## 🎯 Objetivos

- **Diseñar un sistema de planificación** para automatizar la gestión de almacenes
- **Definir formalmente problemas complejos** utilizando lenguaje PDDL
- **Implementar algoritmos de planificación** para encontrar secuencias óptimas de acciones
- **Optimizar rutas y recursos** minimizando tiempo y costos operativos
- **Demostrar aplicación práctica** de IA en logística e industria 4.0
- **Desarrollar prototipo funcional** de coordinación entre múltiples agentes

## 🧠 Conceptos Clave

- **Planning (Planificación)**: Búsqueda de secuencias de acciones para lograr objetivos
- **PDDL (Planning Domain Definition Language)**: Lenguaje formal para especificar problemas
- **Domain Definition**: Descripción de acciones, tipos y predicados disponibles
- **Problem Definition**: Instancia específica con estado inicial y objetivos
- **State Space Search**: Exploración del espacio de estados posibles
- **Graph Planning**: Construcción de grafos de planeamiento
- **Action Ordering**: Determinación del orden óptimo de ejecución
- **Robot Logistics**: Automatización de procesos de almacenaje
- **Multi-agent Planning**: Coordinación entre múltiples robots

## ⚙️ Desarrollo

### Metodología
Se implementa un enfoque formal de IA con dos componentes principales:

#### **Parte 1: Planificación de Almacén (parte1_planificacion_almacen.ipynb)**

1. **Definición del Dominio PDDL**
   - Especificación de tipos: ubicaciones, cajas, robots
   - Definición de predicados: posición, contiene, disponible
   - Implementación de acciones: mover, cargar, descargar
   - Restricciones: capacidad de robots, zonas de almacenamiento

2. **Formulación del Problema**
   - Estado inicial: distribución de cajas en almacén
   - Objetivos: llevar cajas a zonas destino
   - Restricciones operacionales
   - Métricas de optimización

3. **Planificación Automática**
   - Búsqueda en espacio de estados
   - Generación de planes válidos
   - Análisis de calidad de planes
   - Evaluación de coste (pasos, distancia, tiempo)

4. **Evaluación de Soluciones**
   - Métricas de eficiencia
   - Comparativa de estrategias
   - Análisis de factibilidad

#### **Parte 2: Colaboración y Coordinación (parte2_colab.ipynb)**

1. **Planificación Multi-agente**
   - Coordinación de múltiples robots
   - Evitación de conflictos
   - Asignación de tareas distribuida

2. **Optimización Conjunta**
   - Reparto equitativo de carga
   - Minimización de interferencias
   - Sincronización de acciones

3. **Implementación Colaborativa**
   - Algoritmos de negociación entre agentes
   - Resolución de conflictos
   - Planes distribuidos coordinados

### Decisiones Importantes
- **Uso de PDDL**: Permite especificación formal y uso de planificadores públicos
- **Aproximación modular**: Separación clara entre planificación simple y multi-agente
- **Enfoque incremental**: Parte 1 establece base para Parte 2
- **Validación formal**: Verificación de planes antes de ejecución

## 📊 Resultados

El proyecto entrega:
- **Dominio PDDL completo** y reutilizable para problemas similares
- **Planificador automático funcional** que genera planes válidos
- **Análisis de eficiencia** con múltiples estrategias
- **Sistema multi-agente** coordinado y escalable
- **Documentación detallada** de diseño y decisiones
- **Evaluaciones comparativas** entre enfoques

## 🚀 Conclusiones

Este proyecto demuestra la potencia de la planificación automática en logística:

- **PDDL es lenguaje efectivo** para modelar dominios complejos
- **Planificadores automáticos generan soluciones óptimas** rápidamente
- **Multi-agente añade realismo** a problemas de almacenaje
- **Aplicable en producción** a sistemas reales de automatización

**Mejoras futuras:**
- Integración con sensores reales de robots
- Adaptación dinámica a cambios en almacén (new cajas, robots dañados)
- Simulación visual en 3D del almacén y movimientos
- Extensión a optimización de recursos (energía, mantenimiento)
- Integración con sistemas MES/WMS reales

## 📂 Estructura del Proyecto

```
ML II/
├── parte1_planificacion_almacen.ipynb     # Planificación simple de almacén
├── parte2_colab.ipynb                    # Planificación multi-agente colaborativa
├── RA. Machine Learning II.docx.pdf      # Documentación formal del proyecto
└── README.md                             # Este archivo
```

### Contenido de Archivos
- **parte1_planificacion_almacen.ipynb**:
  - Definición formal del dominio PDDL
  - Especificación de problemas de planificación
  - Implementación de planificador simple
  - Evaluación de calidad de planes
  
- **parte2_colab.ipynb**:
  - Extensión a multi-agente
  - Algoritmos de coordinación
  - Resolución de conflictos
  - Pruebas de escalabilidad

## 🛠️ Tecnologías Utilizadas

| Tecnología | Uso |
|-----------|-----|
| **Python 3.x** | Lenguaje principal |
| **PDDL** | Lenguaje de especificación formal |
| **Automated Planning** | Búsqueda y generación de planes |
| **Graph Algorithms** | Algoritmos de grafos para planificación |
| **NumPy** | Operaciones numéricas y matrices |
| **Jupyter Notebook** | Desarrollo interactivo |
| **Simulación Discreta** | Modelado de eventos |

## ✍️ Autor

**Víctor Ferrer**  
Master en Inteligencia Artificial - UTAMED  
*Empresa Simulada: AutoLogistics*

---

*Este proyecto forma parte del programa de posgrado en Inteligencia Artificial y demuestra competencias avanzadas en planificación automática, IA simbólica y optimización de sistemas complejos aplicados a logística industrial.*
