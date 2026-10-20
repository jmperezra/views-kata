# Views Kata 🧩

Repositorio de práctica para aprender a **diseñar interfaces en Android**.

Empezamos por las **vistas clásicas (XML)** y, más adelante, haremos lo mismo con **Jetpack Compose**.

Es una *kata*: ejercicios cortos que se repiten hasta que salen solos. No buscamos una app terminada. Buscamos entender bien cada pieza.

---

## ¿Por qué vistas clásicas si ya existe Compose?

- Muchas apps en producción siguen usando XML. En la empresa te las vas a encontrar.
- En las entrevistas técnicas se pregunta por ellas.
- Entender cómo se mide y se coloca una vista en XML ayuda mucho a entender Compose después.

---

## Objetivos

Al terminar las katas de vistas clásicas deberías saber:

1. **Elegir el layout adecuado** para cada pantalla (`LinearLayout`, `FrameLayout`, `RelativeLayout`, `ConstraintLayout`).
2. **Maquetar a partir de un diseño**: mirar una pantalla y saber cómo dividirla en bloques.
3. **Controlar el tamaño y la posición** de las vistas: `match_parent`, `wrap_content`, márgenes, *padding* y `gravity`.
4. **Usar recursos en lugar de valores fijos**: textos en `strings.xml`, medidas en `dimens.xml`, colores en `colors.xml` y estilos en `styles.xml`.
5. **Usar componentes básicos y de Material**: `TextView`, `EditText`, `Button`, `ImageView`, `MaterialButton`, `ShapeableImageView`, `LinearProgressIndicator`…
6. **Explicar lo que has hecho**. Cada ejercicio debe servirte para contarlo en una entrevista.

---

## Contenido actual

### Enunciados

Los enunciados de los ejercicios están en [`assets/Enunciados.md`](assets/Enunciados.md).

### Layouts

Todos los ejercicios están en `app/src/main/res/layout/`.

| Archivo | Layout | Qué se practica | Estado |
|---|---|---|---|
| `view_linearlayout.xml` | LinearLayout | Ejemplo base: orientación, anidar layouts, `ImageView` con `tint`, `TextView` con `maxLines` y `ellipsize`, `EditText` y `Button` | ✅ |
| `view_ll_ej1.xml` | LinearLayout | Tarjeta de producto: imagen a la izquierda y datos a la derecha | ✅ |
| `view_ll_ej2.xml` | LinearLayout | Tarjeta de evento: `ShapeableImageView` con esquinas cortadas y `MaterialButton` con icono | ✅ |
| `view_ll_ej3.xml` | LinearLayout | Pantalla de detalle: separadores, columnas, barra de progreso y filas clave-valor | ✅ |
| `view_fl_ejemplo1.xml` | FrameLayout | Vistas apiladas unas encima de otras | ✅ |
| `view_relativelayout.xml` | RelativeLayout | Posicionar vistas respecto al padre y a otras vistas (`toEndOf`, `below`, `alignStart`…) | ✅ |
| `view_relativelayout_tetris.xml` | RelativeLayout | Colocar piezas como en el Tetris | 🚧 En curso |
| `view_relativelayout_ej1.xml` | RelativeLayout | Ejercicio de práctica | 🚧 En curso |

---

## Cómo usar el repositorio

1. Clona el repositorio y ábrelo con **Android Studio**.
2. Abre cualquier archivo de `res/layout/`.
3. Usa la vista **Split** o **Design** para ver el resultado sin ejecutar la app.
4. Para verlo en el emulador, cambia el layout en `MainActivity.kt`:

```kotlin
setContentView(R.layout.view_ll_ej1)
```

> ⚠️ `MainActivity` busca una vista con `android:id="@+id/main"` para aplicar los márgenes del sistema (*edge-to-edge*). Si el layout que cargas no la tiene, la app fallará. Añade ese `id` a la vista raíz o comenta ese bloque.

### Cómo trabajar cada ejercicio

1. Lee el enunciado o mira el diseño.
2. Dibuja los bloques en papel antes de escribir XML.
3. Decide qué layout usar y por qué.
4. Maqueta. Primero la estructura, luego los detalles.
5. Saca textos, medidas y colores a recursos.
6. Explica tu solución en voz alta, como si estuvieras en una entrevista.

---

## Conceptos clave

- **`match_parent` vs `wrap_content`**: ocupar todo el espacio del padre o solo lo que necesita el contenido.
- **`dp` vs `sp`**: `dp` para medidas, `sp` para texto (respeta el tamaño de letra del usuario).
- **`margin` vs `padding`**: espacio por fuera de la vista o por dentro.
- **`gravity` vs `layout_gravity`**: cómo coloca una vista su contenido o cómo se coloca ella dentro de su padre.
- **Namespace `tools:`**: datos que solo se ven en el editor, no en la app (por ejemplo, `tools:text`).
- **Anidar layouts tiene coste**: cada nivel extra hace más lento el dibujado. Por eso existe `ConstraintLayout`.

---

## Preguntas típicas de entrevista

- ¿Qué diferencia hay entre `LinearLayout`, `RelativeLayout`, `FrameLayout` y `ConstraintLayout`? ¿Cuándo usarías cada uno?
- ¿Por qué no es buena idea anidar muchos `LinearLayout`?
- ¿Qué es `layout_weight` y cómo funciona?
- ¿Por qué se usan `dp` y `sp` en lugar de píxeles?
- ¿Por qué hay que sacar los textos a `strings.xml`?
- ¿Para qué sirve el namespace `tools:`?
- ¿Qué ventajas tiene Compose frente a las vistas XML? ¿Y qué inconvenientes?

---

## Hoja de ruta

### Vistas clásicas
- [x] LinearLayout
- [x] FrameLayout (introducción)
- [ ] RelativeLayout
- [ ] ConstraintLayout
- [ ] ScrollView
- [ ] RecyclerView
- [ ] Estilos y temas

### Jetpack Compose
- [ ] Column, Row y Box
- [ ] Modifiers
- [ ] Listas con LazyColumn
- [ ] Rehacer en Compose las katas de vistas clásicas

---

## Requisitos técnicos

- Android Studio (versión reciente, compatible con AGP 9)
- `minSdk` 26 · `targetSdk` 37
- Kotlin + vistas XML con AppCompat y Material Components

---

Proyecto creado para el ciclo de **Desarrollo de Aplicaciones Multiplataforma (DAM)** del IES Alonso de Madrigal (Ávila).
