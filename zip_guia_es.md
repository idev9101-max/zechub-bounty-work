# ¿Qué es un ZIP y cómo se crea uno? — Guía para proponer mejoras en Zcash

## Introducción

Zcash es una red descentralizada: no existe un CEO ni un comité central que decida unilateralmente qué cambios entran en el protocolo. En su lugar, el ecosistema usa un proceso abierto y documentado llamado **ZIP — Zcash Improvement Proposal** (propuesta de mejora de Zcash). Cualquier persona —desarrolladora, investigadora o simplemente una usuaria curiosa— puede escribir una propuesta y someterla al escrutinio público.

Esta guía explica qué es un ZIP, por qué importa para la gobernanza de la red, y los pasos concretos para crear y enviar uno desde cero.

## ¿Qué es un ZIP?

Un ZIP es un documento técnico estandarizado que describe un cambio propuesto para Zcash: desde modificaciones del consenso y nuevos campos de transacción hasta procesos de gobernanza o estándares de ecosistema. Los ZIPs se inspiran en los BIP de Bitcoin, pero tienen reglas propias definidas en el **ZIP 0** (el "meta-ZIP" que describe el proceso).

Cada ZIP tiene:

- **Número** asignado por los editores al ser aceptado como borrador (p. ej., ZIP 320, ZIP 316)
- **Categoría**: *Consensus* (afecta las reglas del protocolo), *Standards* (convenciones técnicas), *Process* (cómo se organiza la comunidad) o *Informational* (documentación)
- **Estado**: Draft → Proposed → Active/Final/Rejected/Withdrawn

## ¿Por qué importan los ZIPs?

- **Gobernanza abierta**: toda decisión de consenso queda escrita, discutida en público y versionada.
- **Coordinación entre implementaciones**: zcashd, Zebra y las wallets necesitan una especificación común para no divergir.
- **Memoria institucional**: el razonamiento detrás de cada cambio queda registrado para futuras generaciones de desarrolladores.

## El ciclo de vida de un ZIP

1. **Idea y discusión previa** — Se recomienda debatir la idea en el foro community.zcash.com, en el Discord de Zcash o en reuniones de arborist calls antes de escribir. Una propuesta con apoyo previo tiene muchas más probabilidades de avanzar.
2. **Redacción del documento** — Se escribe en formato reStructuredText siguiendo la plantilla `zip-template.rst` del repositorio. Debe incluir: resumen, motivación, especificación técnica precisa, justificación de decisiones, y consideraciones de seguridad.
3. **Pull request al repositorio** — El ZIP se envía como PR a `github.com/zcash/zips`, numerado provisionalmente según indiquen los editores.
4. **Revisión editorial** — Los editores de ZIPs (actualmente representantes de Electric Coin Co., Zcash Foundation y la comunidad) revisan la corrección técnica, el formato y la completitud. Pueden pedir cambios.
5. **Estado "Proposed"** — Una vez aceptado como draft, el ZIP queda abierto a comentarios de la comunidad.
6. **Activación** — Los ZIPs de consenso requieren implementación y se activan en un network upgrade (NU). El proceso de coordinación se detalla en ZIP 0 y en el calendario de upgrades.

## Pasos concretos para enviar tu ZIP

```bash
git clone https://github.com/zcash/zips
cd zips
cp zip-template.rst zip-XXXX-nombre.rst
# rellena el preámbulo (ZIP, Title, Owners, Status: Draft, Category, Created, License)
git checkout -b mi-propuesta
git add zip-XXXX-nombre.rst && git commit -m "Draft: mi propuesta"
# abre el PR contra main
```

Requisitos clave:

- **Escritura precisa**: la especificación debe ser lo bastante detallada para que otra persona la implemente sin ambigüedades.
- **Rationale**: explica por qué se tomó cada decisión y qué alternativas se descartaron.
- **Compatibilidad**: describe impacto en despliegues existentes y en la piscina de transacciones.
- **Licencia**: el documento debe usar una licencia abierta aceptada (BSD-2-Clause o MIT).

## Consejos prácticos

- Lee ZIP 0 completo antes de escribir; es corto y resuelve el 90% de las dudas.
- Revisa ZIPs aceptados recientes (p. ej., los de NU5/NU6) para ver el nivel de detalle esperado.
- Presenta primero la idea en el foro: si hay oposición de fondo, mejor saberlo antes de escribir 40 páginas.
- Los ZIPs informativos y de proceso tienen barras de entrada más bajas que los de consenso: son una buena primera contribución.

## Recursos

- Repositorio oficial: https://github.com/zcash/zips
- ZIP 0 (el proceso): https://zips.z.cash/zip-0000
- Foro de la comunidad: https://forum.zcashcommunity.com
- Índice de todos los ZIPs: https://zips.z.cash
