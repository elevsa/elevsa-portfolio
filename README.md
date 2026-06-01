# ELEVSA — Portfolio Web · Agente de Asistencia Técnica con IA

> **TFM — Máster en Transformación Digital y Hiperautomatización de Procesos · 2024–2025**

Portfolio web corporativo de **ELEVSA**, empresa ficticia de instalación y mantenimiento de ascensores, desarrollado como parte del Trabajo de Fin de Máster sobre hiperautomatización de procesos empresariales.

---

## 🌐 Demo en vivo

**[https://elevsa.github.io/elevsa-portfolio](https://elevsa.github.io/elevsa-portfolio)**

---

## 📋 Descripción del proyecto

Este repositorio contiene la web corporativa de ELEVSA, que actúa como punto de entrada unificado para dos workflows automatizados desarrollados con **n8n** y un agente conversacional construido con **Cognigy**:

| Canal | Tecnología | Función |
|---|---|---|
| Formulario de incidencias | n8n Hosted Form | Alta automática de averías en Airtable |
| Asistente conversacional | Cognigy Webchat | Recogida de incidencias y diagnóstico orientativo |
| Agente RAG interno | n8n + GPT-4o-mini + Supabase | Asistencia técnica para empleados (PWA separada) |

---

## 🏗️ Arquitectura del sistema completo

```
ELEVSA Portfolio Web (este repo)
│
├── Formulario n8n ──────► Airtable (INCIDENCIAS)
│                                │
│                                ▼
│                     Flujo 2: Guardado automático en RAG
│                                │
│                                ▼
│                     Supabase (knowledge_base + pgvector)
│                                │
└── Agente Cognigy ──────►       ▼
                         Flujo 3: Agente GPT-4o-mini
                                │
                                ▼
                         PWA Técnicos (elevsa-asistente)
```

---

## 🛠️ Stack tecnológico

- **Frontend:** HTML5 + CSS3 vanilla · Sin frameworks · Sin dependencias npm
- **Alojamiento:** GitHub Pages (gratuito, 24/7)
- **Automatización:** n8n (servidor Easypanel compartido)
- **Base de datos vectorial:** Supabase + pgvector
- **LLM:** OpenAI GPT-4o-mini + text-embedding-3-small
- **CRM de incidencias:** Airtable
- **Agente conversacional:** Cognigy
- **Fuente de manuales:** Google Drive

---

## 📁 Estructura del repositorio

```
elevsa-portfolio/
├── index.html          # Web completa (una sola página, autocontenida)
└── README.md           # Este archivo
```

La web es un único archivo `index.html` autocontenido: el logo está embebido en base64 y no requiere archivos externos ni servidor backend.

---

## ⚙️ Configuración de integraciones

### Formulario n8n

En `index.html`, busca el comentario `PARA ACTIVAR EL FORMULARIO N8N` y sustituye el bloque placeholder por:

```html
<iframe
  src="https://tu-n8n.easypanel.host/form/XXXX"
  style="width:100%;height:640px;border:none;display:block">
</iframe>
```

### Agente Cognigy

Busca el comentario `PARA ACTIVAR EL AGENTE COGNIGY` y pega el iframe de tu endpoint:

```html
<iframe
  src="https://webchat.cognigy.ai/..."
  style="width:100%;height:460px;border:none"
  allow="microphone">
</iframe>
```

---

## 🚀 Publicación en GitHub Pages

1. Subir `index.html` a la raíz del repo
2. **Settings → Pages → Branch: main → / (root) → Save**
3. La web queda disponible en `https://elevsa.github.io/elevsa-portfolio/`

---

## 🔗 Repositorios relacionados

| Repo | Descripción |
|---|---|
| [elevsa/elevsa-asistente](https://github.com/elevsa/elevsa-asistente) | PWA móvil con login para técnicos (agente RAG interno) |
| elevsa/elevsa-portfolio *(este repo)* | Web corporativa pública con formulario y agente Cognigy |

---

## 📚 Contexto académico

Este proyecto forma parte de un TFM sobre **hiperautomatización de procesos** que implementa:

- **RPA + IA:** Flujos n8n para ingesta de documentos y gestión de incidencias
- **RAG (Retrieval-Augmented Generation):** Base de conocimiento vectorial sobre manuales técnicos e historial de averías resueltas
- **Agente conversacional omnicanal:** Cognigy para atención al cliente + n8n para asistencia técnica interna
- **PWA:** Interfaz móvil instalable sin App Store para los técnicos de campo

---

*Empresa ficticia creada con fines académicos · ELEVSA no es una empresa real*# elevsa-portfolio
