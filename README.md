# Barlo · update

Lo que la app Barlo baja de internet para mantenerse al día, **firmado por Barlo**:

- los **programas** compilados de los equipos Barlo (central, pantalla y los que vengan);
- las **guías** de las fuentes de datos: dónde publica cada proveedor (por ejemplo, el Servicio de Hidrografía Naval) y cómo leerlo. **Acá no hay datos**: cada teléfono los baja directo del proveedor.

La app lee `ficha.json` cuando el teléfono tiene internet y baja lo nuevo. **Todo se revisa contra la firma de Barlo**: un programa o una guía que no estén firmados, o a los que les cambiaron un solo byte, no se usan. Cada equipo, además, revisa la firma de su programa antes de grabarlo.

- `ficha.json` — lo publicado: los programas (tipo, versión, archivo, suma SHA-256, firma, notas) y las guías (id, versión, archivo, suma, firma).
- `ficha.json.firma` — la firma de la ficha entera.
- `programas/` — los `.bin`.
- `guias/` — las guías (`.json`).

Se publica con `herramientas/firma/firmar.py` (en el repositorio del firmware, privado): `firmar.py <programa.bin>` o `firmar.py --guia <guia.json>`. El código fuente no está acá.

(Antes se llamaba `barlo-programas`.)
