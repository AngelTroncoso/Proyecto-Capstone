# Capstone Project: Conserje_Bot - Sistema Multiagente Inteligente

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Google SDK](https://img.shields.io/badge/Google%20SDK-Latest-orange.svg)
![Kaggle](https://img.shields.io/badge/Platform-Kaggle-20BEFF.svg)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success.svg)

## 📋 Tabla de Contenidos
- [Descripción General](#descripción-general)
- [Arquitectura del Sistema](#arquitectura-del-sistema)
- [Componentes Principales](#componentes-principales)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
---

## 🎯 Descripción General

**Conserje_Bot** es un sistema multiagente inteligente desarrollado como proyecto Capstone que simula un conserje virtual para edificios residenciales. El sistema utiliza el SDK de Google y está implementado completamente en Python, demostrando capacidades avanzadas de procesamiento de lenguaje natural, gestión de conocimiento y coordinación entre múltiples agentes especializados.

### Problemática Abordada

Los edificios residenciales modernos enfrentan desafíos constantes en:
- **Gestión eficiente de solicitudes de mantenimiento**
- **Interpretación y aplicación de reglamentos internos**
- **Provisión de información relevante sobre el vecindario**
- **Disponibilidad 24/7 para atención a inquilinos**

### Solución Propuesta

Un sistema multiagente coordinado que:
- ✅ Responde consultas en lenguaje natural
- ✅ Gestiona solicitudes de mantenimiento inteligentemente
- ✅ Proporciona información precisa sobre reglamentos
- ✅ Ofrece recomendaciones personalizadas del sector

---

## 🏗️ Arquitectura del Sistema
```
┌─────────────────────────────────────────────────┐
│           CONSERJE_BOT (Agente Principal)       │
│                                                  │
│  - Procesamiento de Lenguaje Natural (NLP)      │
│  - Clasificación de Intenciones                 │
│  - Coordinación de Subagentes                   │
│  - Gestión de Conversaciones                    │
└────────────────┬────────────────────────────────┘
                 │
        ┌────────┴────────┐
        │                 │
┌───────▼──────┐  ┌──────▼────────────┐
│   AGENTE DE  │  │  AGENTE           │
│ MANTENIMIENTO│  │  VECINDARIO       │
│              │  │                   │
│ - RAG System │  │ - Recomendaciones │
│ - Reglamento │  │ - Info Local      │
│ - Tickets    │  │ - Servicios       │
└──────────────┘  └───────────────────┘
```

### Flujo de Trabajo

1. **Entrada del Usuario**: El inquilino ingresa una consulta en lenguaje natural
2. **Análisis de Intención**: El Conserje_Bot clasifica la intención usando NLP
3. **Delegación Inteligente**: Envía la solicitud al subagente apropiado
4. **Procesamiento Especializado**: El subagente procesa la consulta con su base de conocimiento
5. **Respuesta Unificada**: El Conserje_Bot consolida y entrega la respuesta al usuario

---

## 🤖 Componentes Principales

### 1. Conserje_Bot (Agente Coordinador)

**Responsabilidades:**
- Interfaz principal con los usuarios
- Clasificación de intenciones mediante modelos NLP
- Routing de consultas a subagentes especializados
- Mantenimiento del contexto conversacional
- Síntesis de respuestas de múltiples agentes

**Tecnologías:**
- Google Cloud Natural Language API
- Dialogflow CX para gestión de diálogos
- BERT fine-tuned para clasificación de intenciones

### 2. Agente de Mantenimiento

**Responsabilidades:**
- Gestión de solicitudes de mantenimiento
- Consulta y aplicación del reglamento interno del edificio
- Generación de tickets de trabajo
- Priorización de solicitudes según normativas
- Seguimiento de estados de reparaciones

**Características Técnicas:**
- **RAG (Retrieval-Augmented Generation)**: Implementado con Vertex AI
- **Base de Conocimiento**: Reglamento interno embebido con embeddings de Google
- **Clasificación de Urgencia**: Modelo ML entrenado con datos históricos
- **Vectorstore**: ChromaDB para búsqueda semántica eficiente

**Ejemplo de Interacción:**
```
Usuario: "¿Puedo hacer una reforma en mi departamento?"
Agente: "Según el artículo 15 del reglamento interno, las reformas 
         requieren aprobación previa del consorcio. Debe presentar 
         planos y obtener autorización en un plazo de 15 días hábiles."
```

### 3. Agente Vecindario

**Responsabilidades:**
- Recomendaciones de servicios locales (restaurantes, farmacias, etc.)
- Información sobre transporte público cercano
- Alertas sobre eventos en el sector
- Sugerencias personalizadas basadas en preferencias del usuario

**Características Técnicas:**
- **Google Maps Platform API**: Para geolocalización y búsqueda de lugares
- **Google Places API**: Información detallada de negocios locales
- **Sistema de Recomendación**: Collaborative filtering con datos de Kaggle
- **Caché Inteligente**: Redis para optimizar consultas repetidas

**Ejemplo de Interacción:**
```
Usuario: "Necesito una farmacia de turno cerca"
Agente: "🏥 Farmacia San José está a 300m (3 min caminando)
         📍 Av. Principal 456
         ⏰ Abierta 24hs
         ⭐ 4.5/5 estrellas (120 reseñas)"
```

---

## 🛠️ Tecnologías Utilizadas

### SDK y APIs de Google
- **Vertex AI**: Para modelos de lenguaje y embeddings
- **Dialogflow CX**: Gestión avanzada de conversaciones
- **Google Cloud Natural Language API**: Análisis de sentimiento y entidades
- **Google Maps Platform**: Geolocalización y recomendaciones
- **Google Places API**: Información de negocios locales
- **Cloud Storage**: Almacenamiento de reglamentos y documentos

### Bibliotecas Python
```python
google-cloud-aiplatform==1.38.0
google-cloud-dialogflow-cx==1.20.0
google-cloud-language==2.11.0
google-maps-services==4.10.0
langchain==0.1.0
chromadb==0.4.18
sentence-transformers==2.2.2
pandas==2.0.3
numpy==1.24.3
scikit-learn==1.3.0
```

### Infraestructura
- **Entorno de Desarrollo**: Kaggle Notebooks (GPU P100)
- **Almacenamiento**: Google Cloud Storage buckets
- **Base de Datos Vectorial**: ChromaDB local con persistencia

---


---

*Última actualización: Noviembre 2025*  
*Versión del README: 2.1*  
*Conserje_Bot - Haciendo los edificios más inteligentes 🏢🤖*

