# capturas-juego

Repositorio para generar capturas reales del proyecto Godot/Statecraft usando GitHub Actions + Xvfb.

## Uso rápido

1. Subí al repo el ZIP final del proyecto, por ejemplo:
   `statecraft_v0_3_16_popup_decision_ux_hover_FINAL.zip`
2. Entrá en la pestaña **Actions**.
3. Abrí el workflow **Capturar Godot con Xvfb**.
4. Tocá **Run workflow**.
5. Cuando termine, descargá el artifact `capturas-godot`.

El workflow descomprime el ZIP, descarga Godot Mono, instala Xvfb, ejecuta la escena de captura y sube los PNG/reportes como artifact.

## ZIP esperado

El ZIP debe contener una carpeta `sc0312/` con `project.godot` adentro.

## Escena principal de captura

Por defecto corre:

```text
res://scenes/testing/GodotNetCSharpDecisionPopupCaptureV0316.tscn
```

Esa escena intenta guardar capturas en:

```text
sc0312/reports/capturas/v0_3_16_popup/
```
