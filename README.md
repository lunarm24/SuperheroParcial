# SuperheroParcial 🦸‍♂️⚡

Aplicación Android desarrollada en **Kotlin** con **Jetpack Compose** que consume la API REST de superhéroes para mostrar un catálogo completo de héroes y el detalle individual de sus estadísticas y biografía.

---

## 📱 Características principales

- **Pantalla de Inicio (Home):**
  - Lista de superhéroes obtenida dinámicamente desde la API REST.
  - Tarjetas personalizadas con imagen, nombre, nombre real/alter ego y editorial.
  - Manejo de estados: Carga (Loading), Error de red con opción de reintento, y Lista vacía.
  - Fallback automático para héroes sin nombre real registrado (*"Identidad desconocida"*).

- **Pantalla de Detalle (Detail):**
  - Vista expandida del superhéroe con imagen en alta calidad.
  - Gráficos/Barras de estadísticas de poder (*Powerstats*: Inteligencia, Fuerza, Velocidad, Durabilidad, Poder, Combate).
  - Navegación fluida de regreso a la lista principal.

---

## 🛠️ Tecnologías y Librerías Utilizadas

- **Lenguaje:** Kotlin
- **UI Framework:** [Jetpack Compose](https://developer.android.com/jetpack/compose) con Material Design 3
- **Inyección de Dependencias:** [Hilt / Dagger](https://developer.android.com/training/dependency-injection/hilt-android)
- **Navegación:** [Navigation Compose](https://developer.android.com/jetpack/compose/navigation)
- **Conexión a Red:** [Retrofit 2](https://square.github.io/retrofit/) + [Gson Converter](https://github.com/google/gson)
- **Carga de Imágenes:** [Coil Compose](https://coil-kt.github.io/coil/compose/)
- **Asincronía y Flujos:** Coroutines + `StateFlow` + `collectAsStateWithLifecycle`
- **Arquitectura:** MVVM (Model-View-ViewModel) + Clean Architecture por capas

---

## 📂 Estructura del Proyecto

```text
com.example.superheroparcial/
├── data/
│   ├── DTO/          # Data Transfer Objects y mapeo desde JSON
│   ├── model/        # Modelos de dominio (Superhero)
│   ├── remote/       # Interfaz Retrofit (SuperheroApi)
│   ├── repository/   # Repositorio (SuperheroRepository e Implementación)
│   └── source/       # Fuente de datos remota (SuperheroDataSource)
├── di/               # Módulos de inyección de dependencias con Hilt (AppModule)
├── navigation/       # Definición de rutas y NavHost (Screen, AppNavigation)
└── ui/
    ├── components/   # Componentes reusables UI (HeroImage, HeroName, ContentStates)
    ├── detail/       # Pantalla de detalle, ViewModel, UI State y componentes
    ├── home/         # Pantalla principal, ViewModel, UI State y componentes
    └── theme/        # Tema Material 3 (Colores, Tipografía, Tema)
```

---

## 🌐 Fuente de Datos (API)

La aplicación consume la API pública de **Akkabab Superhero API**:
- **Base URL:** `https://akabab.github.io/superhero-api/`
- **Endpoints:**
  - `GET api/all.json` - Obtiene la lista completa de superhéroes.
  - `GET api/id/{id}.json` - Obtiene los detalles de un superhéroe específico por ID.

---

## 🚀 Requisitos e Instalación

1. **Requisitos:**
   - Android Studio Ladybug (o superior)
   - JDK 17
   - Dispositivo o Emulador Android con versión 8.0 (API 26) o superior
   - Conexión a Internet

2. **Pasos para ejecutar:**
   - Clona este repositorio o abre la carpeta en Android Studio.
   - Sincroniza el proyecto con Gradle (*Sync Project with Gradle Files*).
   - Ejecuta el proyecto en tu emulador o dispositivo físico presionado **Run (`Shift + F10`)**.
