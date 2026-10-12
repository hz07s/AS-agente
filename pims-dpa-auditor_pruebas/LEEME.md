# Archivos de prueba de la skill pims-dpa-auditor (v1.1)

Contratos ficticios y resultados usados en la validación del informe del TIF.

## contratos/
| Archivo | Caso | Propósito |
|---|---|---|
| dpa_nubeandina.md | NubeAndina (centro de contacto) | Contrato deficiente con fallas críticas sembradas |
| dpa_andescloud_bueno.md | AndesCloud (hosting) | Contrato conforme, para verificar que la escala discrimina |
| dpa_ambiguo_inyeccion.md | DigiServ (addendum) | Cláusulas vagas y un intento de inyección de instrucciones |

## resultados/
| Archivo | Puntaje | Dictamen |
|---|---|---|
| resultado_NubeAndina.json | 22 (riesgo alto) | No recomendable sin enmiendas |
| resultado_AndesCloud.json | 100 (riesgo bajo) | Recomendable |
| resultado_DigiServ.json | 0 (riesgo alto) | No recomendable sin enmiendas |
| informe_DPA_NubeAndina.md | Informe completo de 11 secciones para la doble aprobación (DPO y Legal) | |

## casos_de_prueba.json
Indicaciones de prueba y comportamiento esperado de cada caso.

## Cómo repetir la prueba
1. Instalar la skill `pims-dpa-auditor.skill` (se entrega por separado).
2. Subir uno de los contratos y pedir: "Evalúa este DPA para el registro de proveedores".
3. Para recalcular un resultado de forma determinista (fecha de referencia del informe: 01/10/2026):

```
python scripts/calcular_resultado.py resultado_NubeAndina.json --config assets/config_organizacion.json --fecha-ref 2026-10-01
```

Los contratos son ficticios y fueron redactados por el grupo; no contienen datos personales reales.
