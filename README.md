# capturas-juego

Repositorio para generar capturas reales del proyecto Godot/Statecraft usando GitHub Actions + Xvfb.

## Uso rapido

1. El ZIP subido actualmente se llama:
   `statecraft_v0_3_16_popup_decision_ux_hover_GITHUB_SLIM (1).zip`
2. Entra en la pestana **Actions**.
3. Abri el workflow **Capturar Godot con Xvfb**.
4. Toca **Run workflow**.
5. Deja los valores por defecto y ejecutalo.
6. Cuando termine, el workflow publica las capturas en `captures/latest/` y tambien deja el artifact `capturas-godot`.

El workflow descomprime el ZIP, descarga Godot Mono, instala Xvfb, ejecuta la escena de captura y sube los PNG/reportes como artifact. Tambien corre automaticamente cuando cambia el workflow o se sube un ZIP `statecraft_v0_3_16_popup_decision_ux_hover_GITHUB_SLIM*.zip` en `main`.

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

## Salida fija para revision

El workflow copia la ultima salida visual a:

```text
captures/latest/
```

Archivos esperados:

```text
captures/latest/manifest.json
captures/latest/01_popup_accion_visible_v0316.png
captures/latest/02_popup_oculto_tras_salida_v0316.png
```

Con eso Codex puede leer `manifest.json`, abrir las PNG por ruta fija y seguir iterando la UI sin depender del ZIP de artifact en cada vuelta.
