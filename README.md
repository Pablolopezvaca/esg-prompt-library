# ESG Prompt Library · Biblioteca de Prompts ESG

**42 prompts técnicos bilingües (ES/EN) para profesionales de sostenibilidad que trabajan con IA.**  
*42 bilingual technical prompts (ES/EN) for sustainability professionals working with AI.*

🌐 **[Ver la biblioteca en vivo · Live library → https://pablolopezvaca.github.io/esg-prompt-library/]**

---

## ¿Qué es esto?

La mayoría de prompts de IA para sostenibilidad que circulan en LinkedIn son genéricos: "escríbeme un informe ESG" o "lista 10 KPIs". Sirven para empezar, pero no para el trabajo real.

Una persona que trabaja con métricas ESG necesita que la IA detecte si las emisiones de Scope 3 suman correctamente o saber qué datapoints del VSME le faltan a una PYME antes de que llegue el auditor; o necesita evaluar si el claim de "carbono neutral" de su cliente cumple la Directiva europea 2024/825/UE.

Esta biblioteca llena ese vacío. 42 prompts construidos para profesionales en ESG.

---

## De dónde viene esto

### Fuente 1 — AI Playbook for Sustainability Reporting de Google (diciembre 2025)

El punto de partida fue el **AI Playbook for Sustainability Reporting** de Google, publicado en diciembre de 2025. Documenta cómo el equipo de sostenibilidad de Google integró IA en su ciclo de reporte real después de casi dos años de experimentación.

De ese documento tomé directamente:

| Técnica del AI Playbook | Aplicación en esta biblioteca |
|---|---|
| Persona-based Prompting | El Periodista Escéptico, El Inversor de Impacto, La ONG de Agua |
| Data Cross-reference | Prompt de cruce tabla–fuente para verificación de datos |
| Arithmetic Check | Verificación aritmética Scope 1+2+3 |
| Mock Scoring | Simulación de puntuación de agencia de rating ESG |
| Inquiry Response | Respuesta a cuestionarios de clientes basada en documentos publicados |
| Accessibility Enhancement | Alt-text para gráficos de sostenibilidad (WCAG 2.1) |
| Content Localization | Adaptación regional ES/LATAM con marcos regulatorios locales |
| Reactive Communications | Briefing ejecutivo para ruedas de prensa e inversores |
| Peer Benchmarking | Análisis comparativo contra referentes del sector |

### Fuente 2 — Documentación oficial EFRAG y ISO

Los prompts normativos están basados en documentación oficial:

- **VSME de EFRAG** (diciembre 2024): estándar completo, Supporting Guides oficiales por módulo, Digital Template XBRL v1.1.1 (noviembre 2025 / taxonomía actualizada febrero 2026), y Recomendación de la Comisión Europea (30 julio 2025)
- **Paquete Omnibus I** de la Comisión Europea: impacto en PYMEs y cadena de valor CSRD
- **FDIS ISO 14001:2026**: aprobado por los miembros de ISO, publicación prevista abril 2026, con período de transición de 3 años hasta ~mayo 2029
- **CSRD / ESRS** (E1–E4, S1, G1): estándares europeos de reporte de sostenibilidad corporativa
- **GHG Protocol Corporate Standard** y **ISO 14064-1**: para prompts de huella de carbono y verificación de emisiones
- **Green Claims Directive 2024/825/UE**: para el prompt de validación de reclamaciones ecológicas

### Fuente 3 — Conocimiento normativo europeo aplicado

Los prompts de VSME Comprensivo (C1–C9), ISO 14001:2026 (Cláusulas 4, 6.1.2, 6.3 y 8), y la intersección VSME–CSRD en cadena de valor vienen de formación directa en gestión ambiental y derecho ambiental europeo.

---

## Técnicas de prompting utilizadas

Esta biblioteca aplica sistemáticamente las técnicas del AI Playbook de Google y otras técnicas establecidas de ingeniería de prompts. Cada prompt indica su técnica en la etiqueta del bloque:

### 🎭 Persona-based Prompting *(AI Playbook de Google)*
Asignar un rol experto específico antes de hacer la pregunta. "Actúa como periodista de investigación buscando greenwashing" produce resultados cualitativamente superiores a "revisa este texto". Activa un marco de referencia concreto.

### 🔗 Chain-of-Thought (CoT) *(AI Playbook de Google + técnica estándar)*
Forzar razonamiento paso a paso antes del resultado final: Identificar → Evaluar → Clasificar → Concluir. Reduce alucinaciones y mejora coherencia en análisis normativos complejos.

### 🎯 RACE (Role · Action · Context · Expectation)
Estructura los 4 elementos que toda IA necesita para producir outputs profesionales: quién es, qué debe hacer, con qué información trabaja, y en qué formato exacto debe entregar el resultado.

### 📝 Few-Shot con ejemplos del Supporting Guide oficial
Proporcionar un ejemplo del formato y nivel de detalle esperado antes del prompt real. Especialmente útil en prompts VSME donde el Supporting Guide de EFRAG tiene ejemplos oficiales que la IA puede usar como referencia.

### 🔄 Iterative Prompting
Estructurar el prompt en iteraciones numeradas (Iteración 1 → 2 → 3 → 4) para tareas complejas que requieren análisis progresivo. Evita respuestas superficiales en análisis de transición normativa.

### 🚫 Grounding (Restricción de fuentes) *(AI Playbook de Google)*
Limitar explícitamente a la IA a trabajar con los documentos proporcionados. "Responde usando ÚNICAMENTE los documentos adjuntos" elimina alucinaciones en prompts de respuesta a cuestionarios.

### 📋 Formato de salida definido
Especificar el formato exacto del output (tabla con columnas concretas, briefing estructurado, roadmap por fases). Hace el resultado directamente usable sin postprocesamiento.

---

## Estructura de la biblioteca (42 prompts · 9 categorías)

| # | Categoría | Prompts | Técnicas principales | Estándares |
|---|-----------|---------|---------------------|------------|
| 1 | Análisis de Brechas | 3 | Chain-of-Thought, Role-based | VSME, CSRD/ESRS, GRI |
| 2 | Verificación de Datos | 3 | Cross-reference, Arithmetic Check (Google) | GHG Protocol, ISO 14064 |
| 3 | Redacción y Revisión | 6 | Persona-based, Grounding, RACE | CSRD, Green Claims Dir. |
| 4 | ISO 14001 · Huella de Carbono | 3 | RACE, Chain-of-Thought | ISO 14001:2015, GHG Protocol |
| 5 | ESRS Temáticos (E1–E4, S1, G1) | 6 | RACE, Chain-of-Thought | CSRD/ESRS |
| 6 | Técnicas AI Playbook Google | 6 | Mock Scoring, Inquiry Response, Localization | General |
| 7 | VSME Básico (Módulo B y T) | 3 | RACE, Iterative | VSME/EFRAG 2024 |
| 8 | VSME Comprensivo (C1–C9 · XBRL) | 6 | RACE, Few-Shot, CoT, Iterative | VSME/EFRAG · Omnibus 2025 |
| 9 | ISO 14001:2026 · Transición | 6 | RACE, CoT, Few-Shot, Iterative | ISO 14001:2026 FDIS |

Todos los prompts están disponibles en **español e inglés** con botón de copia independiente para cada idioma.

---

## Cómo usar los prompts

Cada prompt tiene partes entre corchetes como `[NOMBRE DE LA EMPRESA]` o `[PEGAR TABLA]`. Reemplázalos con tu información real antes de pegarlo en Claude, ChatGPT, Gemini o cualquier IA.

Los prompts están diseñados para que la IA trabaje con **información que tú le proporcionas**, no para que invente datos. Una IA con tus datos reales produce resultados útiles.

**Niveles de dificultad:**
- 🟢 **Básico** — usable directamente sin contexto extenso previo
- 🟡 **Avanzado** — requiere tener datos o documentos listos para proporcionar
- 🔴 **Experto** — requiere conocimiento del estándar para interpretar correctamente el output

---

## Nota sobre ISO 14001:2026

El FDIS (Final Draft International Standard) de ISO 14001:2026 fue aprobado por los miembros de ISO y su publicación está prevista para abril de 2026, reemplazando a ISO 14001:2015. El período de transición propuesto es de 3 años (~mayo 2029). Los prompts de la Sección 9 están basados en los cambios del FDIS: nueva Cláusula 6.3, énfasis en biodiversidad y recursos naturales, perspectiva de ciclo de vida reforzada, y alcance ampliado de la Cláusula 8. Si tienes acceso al texto final publicado, contrasta los prompts con él.

---

## Una advertencia importante

Estos prompts son un **primer filtro**, no una auditoría final.

El propio AI Playbook de Google lo dice: *"AI is a collaborator, not a replacement. You must remain the pilot rather than the passenger."* Ningún output de IA sobre CSRD, VSME o ISO 14001 debería publicarse sin revisión humana experta, especialmente en lo que tenga implicaciones legales o de reporte regulatorio.

---

## Por qué lo hago público

La mayor barrera para que las PYMEs europeas adopten buenas prácticas de reporte ESG no es la voluntad: es la complejidad técnica y el coste de acceso a expertise especializado.

Si esta biblioteca le ayuda a un equipo interno a prepararse mejor para una auditoría, o a un consultor a dedicar menos tiempo al trabajo repetitivo y más al análisis, cumplió su propósito.

---

## Estado del proyecto

- [x] v1.0 — 42 prompts · 9 categorías · VSME Comprensivo (C1–C9 · XBRL v1.1.1) · ISO 14001:2026 FDIS · Omnibus 2025
- [ ] v1.1 — ESRS E5 (Economía Circular) · S2–S4 (Cadena de Valor Social) · E2 Contaminación ampliado
- [ ] v2.0 — Herramienta interactiva: diagnóstico VSME guiado sin necesidad de conocer el estándar

---

## Sobre mí

Soy **Pablo Isaac López Vaca**, técnico en gestión ambiental y especialista en cumplimiento normativo ESG, radicado en Bizkaia (Euskadi). Vengo del derecho ambiental y la gestión pública en Ecuador, y me he recualificado en Euskadi con foco en la normativa ambiental europea, análisis de datos y aplicación práctica de IA en sostenibilidad.

Este proyecto forma parte de la microcredencial en IA Generativa de la USAL así como para posicionarme en la intersección entre **cumplimiento normativo ESG** y **herramientas de IA aplicadas** — especialmente para el mercado español y latinoamericano.

- 🔗 LinkedIn: [linkedin.com/in/tu-perfil](https://www.linkedin.com/in/pablolopezvaca/)
- 💻 GitHub: [github.com/tu-usuario](https://github.com/Pablolopezvaca)

---

## Licencia

Uso libre para fines profesionales y educativos. Se agradece atribución en usos comerciales o publicaciones.

---

*Última actualización: marzo 2026 · v1.2 · 42 prompts · 9 categorías*
