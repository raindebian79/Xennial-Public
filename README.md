# 🏥 Xennial — Sistema Integral de Gestión Clínica

## 🚀 Descripción
**Xennial** es una plataforma web orientada a clínicas y consultorios médicos que centraliza la gestión de pacientes, agenda médica y facturación electrónica en un solo sistema.

Diseñado para entornos reales de producción, el sistema separa claramente las operaciones clínicas de las administrativas, garantizando integridad de datos, trazabilidad y eficiencia operativa.

---

## 🧠 Problema que resuelve
En muchos centros médicos, la información se encuentra fragmentada entre múltiples herramientas o procesos manuales, lo que genera:

- Pérdida de información clínica
- Errores en facturación
- Dificultad en seguimiento de pacientes
- Procesos administrativos ineficientes

**Xennial** unifica estos procesos en una sola plataforma, mejorando la productividad y reduciendo errores humanos.

---

## ⚙️ Módulos Principales

### 🩺 Expediente Médico
- Gestión completa de pacientes
- Historial clínico estructurado
- Registro de signos vitales y antecedentes
- Manejo de documentos médicos (PDFs en nube/local)
- Visualización 3D interactiva de órganos con anotaciones
- Odontograma digital tipo EDUS
- Asociación automática de resultados de Biopsias en citas médicas
- Integración de reportes médicos. 
- Generación de información gráfica y estadística de pacientes para la planificación de servicios. 

### 📅 Agenda Electrónica
- Calendario interactivo con múltiples vistas
- Gestión de citas médicas
- Control de disponibilidad en tiempo real
- Prevención de conflictos de agenda (overbooking)
- Gestión de profesionales y servicios

### 💳 Facturación Electrónica
- Generación de comprobantes electrónicos
- Integración con sistemas fiscales
- Manejo de múltiples tipos de documentos
- Cálculo automático de impuestos y descuentos
- Control de pagos (efectivo, tarjeta, transferencias)
- Módulo de control y gestión de activos fijos con cálculo de depreciación
- Procesamiento automático de correos electrónicos de compras para extracción y registro de información
- Generación de reportes fiscales (IVA y renta) y exportación de información contable en formatos compatibles (Excel) para uso contable
- Módulo de gestión de alertas automáticas para el monitoreo de procesos incompletos, pendientes o fallidos

---

## 🤖 Integración de Inteligencia Artificial

### Asistente de Clasificación Médica
- Procesamiento de lenguaje natural para identificar síntomas
- Clasificación automática de descripciones clínicas
- Sistema de reintentos mediante colas si el servicio no responde
- Registro de resultados para auditoría y mejora continua

### 🎙️ Asistente de Voz por Telegram
Bot de Telegram para consultar y operar Xennial con notas de voz o texto. Los modelos de IA corren en un servidor propio con GPU, sin enviar el audio ni los pedidos a servicios de IA externos.

- Transcripción de voz a texto con Whisper (faster-whisper large-v3) acelerado por GPU
- Interpretación de pedidos con un modelo de lenguaje local (Ollama) y salida en JSON estructurado; la IA solo extrae los datos, y las fechas, impuestos y totales los calcula el sistema
- **Facturación por voz:** identifica al cliente por cédula o por nombre y los productos del catálogo con búsqueda tolerante a errores de transcripción; cuando hay ambigüedad pregunta con botones y nunca deja una factura incompleta
- **Proformas:** cada pedido confirmado queda como proforma pendiente de revisión, con vigencia configurable, cuenta regresiva, renovación y alertas en el sistema. La emisión ante Hacienda es siempre manual desde el formulario de facturación
- **Consultas:** historial de citas de un paciente, agenda del día, conteo de procedimientos por rango de fechas y catálogo de servicios con precios
- **Multiclínica:** un mismo usuario puede trabajar con varias clínicas y elegir con cuál por voz o por comando
- Transcripción de notas de voz en grupos de trabajo autorizados
- **Seguridad:** lista blanca de usuarios, token independiente por clínica, límites de consultas y respuestas con datos mínimos, sin información clínica sensible

---

## 🧩 Arquitectura del Sistema

El sistema está diseñado bajo principios de:

- Separación por capas (servicios, controladores, modelos)
- Encapsulación de lógica de negocio
- Uso de transacciones para operaciones críticas
- Procesamiento asíncrono mediante colas
- Integración con servicios externos mediante APIs

---

## 🛠️ Stack Tecnológico

- **Backend:** Laravel (PHP)
- **Frontend:** Blade, Tailwind CSS, Alpine.js
- **Componentes reactivos:** Livewire
- **Base de datos:** MySQL / MariaDB
- **Build Tools:** Vite
- **IA local:** Python, faster-whisper (Whisper), Ollama
- **Mensajería:** Telegram Bot API

### Librerías destacadas
- spatie/laravel-permission
- spatie/laravel-activitylog
- filament/filament
- maatwebsite/excel
- dompdf/dompdf
- openai-php/client

---

## 🧠 Retos técnicos abordados

- Consistencia entre datos clínicos y financieros
- Integración con APIs externas (MdH, BCCR, Registro Civil)
- Manejo de procesos asíncronos y reintentos
- Optimización de consultas SQL complejas
- Diseño modular y escalable
- Ejecución de modelos de voz y lenguaje en infraestructura propia con GPU
- Interpretación confiable de lenguaje natural: la IA describe el pedido y la lógica de negocio calcula y valida

---

## 💾 Infraestructura y rendimiento

El sistema está preparado para entornos de producción con:

- Manejo de colas para procesos en segundo plano
- Uso de caché y sesiones optimizadas
- Automatización de tareas programadas
- Almacenamiento de archivos en la nube
- Estrategia de respaldos automatizados

> La configuración detallada de infraestructura y despliegue se mantiene privada.

---

## 📸 Capturas del sistema

### 🧭 Dashboard
<img src="Dashboard.png" width="800">

---

### 🩺 Expediente Médico
<img src="Expediente-1.png" width="800">
<img src="Expediente-2.png" width="800">
<img src="Expediente-3.png" width="800">
<img src="Expediente-4.png" width="800">
<img src="Expediente-5.png" width="800">

---

### 📅 Agenda Electrónica
<img src="Agenda-1.png" width="800">

---

### 💳 Facturación Electrónica
<img src="Facturacion-1.png" width="800">
<img src="Facturacion-2.png" width="800">
<img src="Facturacion-3.png" width="800">

---

## 🔒 Código fuente

Este repositorio es únicamente demostrativo y no contiene el código fuente completo.

> El acceso al código está restringido debido a que el sistema maneja lógica de negocio sensible y procesos clínicos/financieros.

---

## 📬 Contacto

Si deseas conocer más sobre el proyecto o solicitar una demostración técnica:

- LinkedIn: *https://www.linkedin.com/in/rainol-azofeifa-37736028a/*
- Email: *info@raindebian.net*

---

## ⭐ Notas finales

Este proyecto representa un sistema real en producción con múltiples módulos integrados, enfocado en resolver necesidades críticas del sector salud mediante tecnología moderna y arquitectura escalable.
