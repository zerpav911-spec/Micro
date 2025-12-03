## Esquema

├── [Paquete Raíz del Proyecto] 
│   ├── app/
│   │   ├── __init__.py         <-- (Define 'app' como un paquete de Python)
│   │   ├── scripts/            <-- (Contiene el punto de inicio del programa)
│   │   │   └── run.py          <-- (Script principal de ejecución)
│   │   └── src/                <-- (Contiene el código fuente modular)
│   │       └── signal/         <-- (Módulo de procesamiento de señal)
│   │           ├── signal.py   
│   │           └── __init__.py 
│   ├── venv/                   <-- (Entorno virtual - IGNORADO por Git)
│   └── requirements.txt        <-- (Lista de dependencias)

### 1. Carpeta de Ejecución (`scripts/`)

#### `run.py` (dentro de `app/scripts/`)
* **¿Para qué sirve?** Actúa como el **punto de entrada** y el **controlador principal** del programa. Es el archivo que se ejecuta para iniciar el proyecto.
* **¿Cómo funciona?** Contiene la lógica para la detección de puertos seriales, la inicialización de la clase de señal y la gestión del flujo principal de datos (como la visualización o el *streaming*).

### 2. Módulo Principal (`src/signal/`)

#### `__init__.py` (dentro de `/signal/`)
* **¿Para qué sirve?** Convierte el directorio `signal` en un **submódulo**.
* **¿Cómo funciona?** Se ejecuta al importar el submódulo y controla qué partes de `signal.py` se exponen.

#### `signal.py` (dentro de `app/src/signal/`)
* **¿Para qué sirve?** Contiene funciones y clases para **procesamiento y manejo de la señal** (comunicación serial, filtrado o análisis básico).
* **¿Cómo funciona?** Implementa la lógica que interactúa con PySerial y maneja los datos recibidos. Es el núcleo funcional del submódulo `signal`.

### 3. Archivos de Paquete (`__init__.py` Raíz)

#### `__init__.py` (en `/app/`)
* **¿Para qué sirve?** Indica que el directorio `app` debe ser tratado como un **paquete de Python**.
* **¿Cómo funciona?** Se ejecuta cuando se importa el paquete y puede controlar qué submódulos se exportan (por ejemplo, definiendo la lista `__all__ = ['src']`).

---