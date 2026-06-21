# AXIS OS — Prototipo UI

Plataforma de gestión técnica de obras para dirección de ejecución (DEO) en España.  
Stack actual: HTML/CSS/JS puro · Sin dependencias externas · BC3/FIEBDC-3 compatible.

## Estructura de archivos

```
axis_shell.html           ← PUNTO DE ENTRADA — abre este archivo
│
├── axis_actas.html           Módulo de actas de visita + transcripción IA
├── axis_ordenes.html         Libro de órdenes de obra
├── axis_incidencias.html     Gestión de incidencias (kanban + lista)
├── axis_certificacion.html   Certificación mensual + criterios
├── axis_documentacion.html   Gestión documental por sistemas
├── axis_clasificacion.html   Clasificación IA de sistemas constructivos
├── axis_medicion_partida.html Medición granular (%, cantidad, línea BC3)
├── axis_nueva_obra.html       Flujo de creación de obra (5 pasos)
└── axis_visor_doc.html        Visor PDF con comparador de versiones
```

Archivos standalone (no integrados en la shell aún):

```
axis_dashboard_doc.html   Dashboard de estado documental
axis_motor_ia.html        Motor de clasificación IA (requiere API key)
```

## Cómo usar

1. Descarga todos los archivos en una carpeta local
1. Abre `axis_shell.html` en el navegador
1. Navega entre módulos desde el sidebar

> Los módulos cargan en iframe. Todos los archivos deben estar en la **misma carpeta**.

## Módulos integrados

|Módulo           |Archivo                |Estado                       |
|-----------------|-----------------------|-----------------------------|
|Shell + Dashboard|axis_shell.html        |✓ Integrado                  |
|Actas de visita  |axis_actas.html        |✓ Integrado                  |
|Órdenes de obra  |axis_ordenes.html      |✓ Integrado                  |
|Incidencias      |axis_incidencias.html  |✓ Integrado                  |
|Certificación    |axis_certificacion.html|✓ Integrado                  |
|Documentación    |axis_documentacion.html|✓ Integrado                  |
|Sistemas         |axis_clasificacion.html|✓ Integrado                  |
|Nueva obra       |axis_nueva_obra.html   |Placeholder → abre standalone|
|Criterios        |axis_certificacion.html|Tab interno                  |
|Calidad          |—                      |Pendiente                    |
|Agentes          |—                      |Pendiente                    |

## Contexto técnico

- **BC3/FIEBDC-3** como único punto de entrada en MVP
- Parser BC3 funcional (Python) en repositorio separado
- Motor de clasificación IA usa Anthropic Claude API
- Schema PostgreSQL v2 con JSONB disponible separadamente
- Transcripción de actas: OpenAI Whisper API + AssemblyAI (diarization)

## Estado del proyecto

MVP en desarrollo. Prototipos de UI validados.  
Backend (FastAPI + PostgreSQL) pendiente de implementación.