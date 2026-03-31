# Apuntes U2

## 2.1 Definición conceptual de componentes, paquetes / librerías

Los componentes de Python se estructuran jerárquicamente en módulos (archivos .py con funciones), paquetes (carpetas que agrupan módulos con un archivo __init__.py) y librerías (colecciones de paquetes). Estas herramientas permiten organizar el código, reutilizar funciones y añadir funcionalidades (como Pandas, Flask o NumPy) usando import y pip.


**Componentes Estructurales**

- Módulo: Es un archivo que contiene código Python (.py), funciones o variables. Facilita la encapsulación.
- Paquete: Una carpeta contenedora de módulos que incluye un archivo especial __init__.py. Esto permite una organización jerárquica.
- Librería: Conjunto de paquetes relacionados que proporcionan funcionalidades específicas (ej: librería estándar de Python, o librerías de terceros).

**Gestión de Librerías**
- Instalación: Se utilizan herramientas como pip para instalar librerías externas desde el repositorio PyPI.
- Importación: Se incorporan al script usando import nombre_libreria o from paquete import modulo.
- Organización: Los paquetes permiten crear espacios de nombres, evitando conflictos de nombres (ej: paquete.subpaquete.modulo).

## 2.2 Uso de librerías proporcionadas por el lenguaje.
Las librerías de Python son conjuntos de módulos preescritos que facilitan la programación, reutilizando código para tareas específicas sin necesidad de reescribirlo. 

Principales Librerías por Ámbito.

**Ciencia de Datos y Análisis:**
- NumPy: Esencial para cálculo numérico, matrices y arreglos multidimensionales.
- Pandas: Clave para manipulación y análisis de datos estructurados (DataFrames).
- Polars: Librería rápida para manipulación de datos.

**Visualización de Datos:**
- Matplotlib: La librería base para gráficos estáticos, interactivos y animados.
- Seaborn: Basada en Matplotlib, ofrece gráficos estadísticos más atractivos.
- Plotly: Para visualizaciones interactivas.

**Machine Learning y AI:**
- Scikit-learn: La referencia para algoritmos de clasificación, regresión y clustering.
- TensorFlow/Keras: Muy utilizados para redes neuronales y Deep Learning.
- PyTorch: Biblioteca clave en Deep Learning.
- XGBoost/LightGBM: Fundamentales para algoritmos en datos tabulares.

**Desarrollo Web y APIs:**
- Requests: La mejor opción para hacer peticiones HTTP e interactuar con APIs.
- Django/Flask: Frameworks esenciales para desarrollo web.

**Automatización y Web Scraping:**
- Selenium: Automatización de navegadores y pruebas.
- Beautiful Soup/Scrapy: Para extraer información de sitios web.
- PyAutoGUI: Automatización de teclado y ratón.

**Otras utilidades:**
- SQLAlchemy: ORM para operaciones de bases de datos SQL.
- NLTK: Procesamiento de lenguaje natural (NLP).
- Faker: Generación de datos falsos.

## 2.3 Creación de componentes (visuales y no visuales) definidos por el usuario
La creación de componentes personalizados en Python, especialmente usando tkinter, implica heredar de clases existentes (Frame, Button, etc.) para encapsular funcionalidad visual o lógica. Los componentes visuales crean interfaces (GUI), mientras que los no visuales gestionan lógica, datos o comportamientos en segundo plano, maximizando la reutilización de código. 
- **Componentes Visuales (Widgets personalizados):**
   - Se definen creando una clase que hereda de un widget de tkinter (como tk.Frame o tk.Button).
   - Permiten agrupar múltiples widgets (ej. un campo de texto con etiqueta) en un solo componente reutilizable.
   - Se utiliza el método __init__ para definir la apariencia y comportamiento predeterminados.

- **Componentes No Visuales (Lógica personalizada):**
  - Son clases que no heredan de elementos gráficos, sino que encapsulan lógica de negocio, conexiones a bases de datos o validaciones de datos.
  - Interactúan con los componentes visuales para actualizar la interfaz.
  - Herencia y Reutilización: La técnica fundamental es la herencia, que permite ampliar las posibilidades de componentes existentes o personalizar su comportamiento.

## 2.4 Creación y uso de paquetes/librerías definidas por el usuario.  
La creación de paquetes o librerías definidas por el usuario consiste en organizar y agrupar código propio (funciones, clases o componentes) en estructuras reutilizables que pueden ser utilizadas en diferentes partes de una aplicación o incluso en otros proyectos.Es decir, en lugar de escribir todo el código en un solo archivo, se deben crear módulos organizados que cumplen funciones específicas.

Este proceso se basa en tres principios fundamentales:
- Modularidad : dividir el sistema en partes pequeñas
- Reutilización : usar el mismo código múltiples veces
- Organización : estructurar correctamente el proyecto

**Crear una librería o paquete implica:**
- Identificar funcionalidades que se repiten o pueden reutilizarse
- Separarlas del programa principal
- Agruparlas en módulos independientes
- Organizarlas dentro de una estructura lógica.

### Ejemplo 
En el siguiente codigo se muestra la implementacion de los conceptos clave que se definieron anteriormente.
``` python
import matplotlib.pyplot as plt
import flet as ft
import flet_charts as fch
import random


# ---------- FUNCIONES DE GRAFICAS ----------

def generar_grafica_barras():
    productos = ["A", "B", "C", "D"]
    ventas = [random.randint(10, 50) for _ in range(4)]

    fig, ax = plt.subplots(figsize=(3, 2.5))
    ax.bar(productos, ventas, color="skyblue")
    ax.set_title("Ventas por producto", fontsize=10, weight="bold")

    plt.tight_layout()
    return fig


def generar_grafica_lineas():
    meses = ["Ene", "Feb", "Mar", "Abr", "May"]
    rendimiento = [random.randint(10, 50) for _ in range(5)]

    fig, ax = plt.subplots(figsize=(3, 2.5))
    ax.plot(meses, rendimiento, color="orange", marker="o", linewidth=2)
    ax.set_title("Tendencia de Rendimiento", fontsize=10, weight="bold")
    ax.grid(True, linestyle="--", alpha=0.6)

    plt.tight_layout()
    return fig


def generar_grafica_dispersion():
    x = [i for i in range(20)]
    y = [random.randint(10, 50) for _ in range(20)]

    fig, ax = plt.subplots(figsize=(3, 2.5))
    ax.scatter(x, y, color="purple", alpha=0.6, edgecolors="white")
    ax.set_title("Muestreo de sensores", fontsize=10, weight="bold")

    plt.tight_layout()
    return fig


def generar_grafica_pastel():
    categorias = ["Fresa", "Chocolate", "Vainilla", "Cafe"]
    valores = [random.randint(10, 40) for _ in range(4)]

    colores = ["#FFB6C1", "#AEC6CF", "#C1E1C1", "#FFFACD"]

    fig, ax = plt.subplots(figsize=(3, 2.5))

    ax.pie(
        valores,
        labels=categorias,
        autopct="%1.1f%%",
        startangle=90,
        colors=colores
    )

    ax.set_title("Distribución de ventas", fontsize=10, weight="bold")

    plt.tight_layout()
    return fig


# ---------- INTERFAZ ----------

def main(page: ft.Page):

    page.title = "Dashboard TAP"
    page.theme_mode = "light"
    page.vertical_alignment = "start"
    page.horizontal_alignment = "center"

    header = ft.Text(
        "Dashboard de Visualización de Datos",
        size=24,
        weight="bold"
    )

    tablero = ft.GridView(
        expand=True,
        runs_count=2,
        spacing=20,
        run_spacing=20,
        child_aspect_ratio=1.5
    )

    # CONTENEDORES CON GRAFICAS

    contenedor_1 = ft.Container(
        content=fch.MatplotlibChart(figure=generar_grafica_barras()),
        border=ft.border.all(1, "black12"),
        border_radius=10,
        padding=5
    )

    contenedor_2 = ft.Container(
        content=fch.MatplotlibChart(figure=generar_grafica_lineas()),
        border=ft.border.all(1, "black12"),
        border_radius=10,
        padding=5
    )

    contenedor_3 = ft.Container(
        content=fch.MatplotlibChart(figure=generar_grafica_dispersion()),
        border=ft.border.all(1, "black12"),
        border_radius=10,
        padding=5
    )

    contenedor_4 = ft.Container(
        content=fch.MatplotlibChart(figure=generar_grafica_pastel()),
        border=ft.border.all(1, "black12"),
        border_radius=10,
        padding=5
    )

    tablero.controls.extend([
        contenedor_1,
        contenedor_2,
        contenedor_3,
        contenedor_4
    ])


    # ---------- BOTON ACTUALIZAR ----------

    def actualizar(e):

        contenedor_1.content = fch.MatplotlibChart(
            figure=generar_grafica_barras()
        )

        contenedor_2.content = fch.MatplotlibChart(
            figure=generar_grafica_lineas()
        )

        contenedor_3.content = fch.MatplotlibChart(
            figure=generar_grafica_dispersion()
        )

        contenedor_4.content = fch.MatplotlibChart(
            figure=generar_grafica_pastel()
        )

        page.update()


    boton_actualizar = ft.ElevatedButton(
        "Actualizar gráficas",
        icon=ft.Icons.REFRESH,
        on_click=actualizar
    )

    page.add(
        header,
        boton_actualizar,
        ft.Divider(),
        tablero
    )


ft.app(target=main)
```
<img width="472" height="400" alt="image" src="https://github.com/user-attachments/assets/e1bb04a9-a132-42e2-a1a3-148fa886cc25" />
<img width="472" height="400" alt="image" src="https://github.com/user-attachments/assets/48bbce3d-5f5f-4017-a746-d09f12f74031" />

# Referencias bibliograficas
- Ali, M. (2025, December 23). Las 31 mejores bibliotecas de Python para la ciencia de datos en 2026. https://www.datacamp.com/es/blog/top-python-libraries-for-data-science
- De Los Santos, P. R. (2023, June 29). Python para todos (3): ScyPy, NumPy, Pandas . . .¿Qué librerías necesitamos? Telefónica Tech. https://telefonicatech.com/blog/python-todos-3-librerias
- Gonzalez, E. (n.d.). 3.4 CREACION DE COMPONENTES (VISUALES y NO VISUALES) DEFINIDO POR EL USUARIO. https://progitca.blogspot.com/2012/03/cerro-azul-ver-instituto-tecnologico-de.html
- Muñoz, J. L. G. (2025, April 29). Librerías de Python: Qué son, para qué sirven y cuáles debes conocer - ESEID AI Business School. ESEID AI Business School. https://eseid.com/librerias-de-python/
