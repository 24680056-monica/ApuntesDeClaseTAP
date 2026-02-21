# ApuntesDeClaseTAP
La Interfaz Gráfica de Usuario es el conjunto de elementos visuales que permiten la comunicación entre el hombre y la máquina. En este caso, utilizamos a Flet al ser un framework para Python que permite crear aplicaciones multiplataforma (escritorio, web y móvil) con interfaces modernas basadas en Flutter. Esto nos facilita al permitirnos diseñar apps visuales, responsivas y con actualizaciones en tiempo real utilizando componentes como contenedores, botones y campos de texto con pocas líneas de código.

## 1.1 Creación de Interfaz Gráfica para Usuarios 
Flet rompe con el esquema tradicional de desarrollo (donde sueles necesitar HTML/JS para web o Swift/Kotlin para móvil). Se basa en el modelo de Programación Declarativa y el motor de Flutter.
<ul>
  <li>El Árbol de Controles: Al igual que en la bibliografía de desarrollo moderno, Flet organiza la interfaz en una estructura de árbol. Cada elemento es un objeto que hereda de una clase base.</li>
  <li>Abstracción de Controles: No dibujamos píxeles; instanciamos objetos como <code>ft.ElevatedButton()</code> o <code>ft.TextField()</code>. Flet se encarga de traducir estos objetos a componentes nativos de la plataforma donde se ejecute.</li>
  <li>El Contenedor <code>Page</code>: Es la raíz de nuestra aplicación. En términos de diseño, es el "View" en un patrón similar a MVC (Modelo-Vista-Controlador).</li>
</ul>
<strong> Pasos básicos para Interfaz Gráfica con Flet </strong>
<ol>
  <li>  Instalación: Ejecutar <code> pip install </code> flet en la terminal.
  <li> Estructura básica: Importar flet, definir una función principal (<code>main</code>) y añadir controles (<code>ft.Text</code>, <code>ft.ElevatedButton</code>, etc.) a la página.</li>
  <li> Ejecución: Usar <code>ft.app(target=main)</code> para iniciar la aplicación, ya sea en modo escritorio o en el navegador.</li>
  <li> Componentes y Layout: Utilizar contenedores (<code>Container</code>), filas (<code>Row</code>), columnas (<ode>Column</ode>) y diseño responsivo (<code>ResponsiveRow</code>) para estructurar la interfaz.</li>
  <li> Eventos: Gestionar interacciones (clics, cambios de texto) mediante funciones para actualizar la UI dinámicamente. </li>
</ol>

## 1.2 Tipos de Eventos 
Un evento es una acción reconocida por el software que puede ser manejada por el programa. En la documentación de Flet, los eventos son objetos de datos que contienen información sobre lo que pasó. Los diferentes tipos de eventos que ocurren son:
<ul>
  <li>Eventos de Clic (<code>on_click</code>): Se dispara al hacer clic sobre un componente como un <code> ElevatedButton, IconButton</code>, o contenedores.</li>
  <li>Eventos de Cambio (<code>on_change</code>): Se activa cuando el valor de un control cambia, común en <code>TextField, Slider, Dropdown o Checkbox</code>.</li>
  <li>Eventos de Entrada (<code>on_submit</code>): Se dispara al presionar Enter en un <code>TextField.</code></li>
  <li>Eventos de Ciclo de Vida (<code>on_app_lifecycle_state_change</code>): Escucha cambios en el estado de la aplicación (SHOW, RESUME, HIDE, PAUSE, etc.) en web y móvil.</li>
  <li>Eventos de Arrastrar y Soltar (<code>on_drag, on_drop</code>): Utilizados para gestionar el movimiento de elementos. </li>
</ul>

## 1.3 Manejo de eventos (Event Handling) 
El manejo de eventos en Flet permite crear interfaces de usuario interactivas y receptivas al reaccionar a acciones del usuario, como clics, entradas de texto, cambios de estado, entre otros. Flet utiliza un modelo declarativo donde las funciones controladores de eventos (event handlers) responden a los cambios en la interfaz. 
<ul>
  <li>Registro: Se asigna una función al atributo del control (ej. <code>on_click=mi_funcion</code>).</li>
  <li>Captura: Flet escucha la interacción del usuario.</li>
  <li>Respuesta: Se ejecuta la lógica en Python. Aquí es donde entra el concepto de Estado: para que la GUI refleje un cambio en las variables, debemos invocar <code>page.update()</code>.</li>
</ul>

## 1.4 Manejo de Componentes Gráficos de Control 
<p> Los componentes de control son las piezas con las que el usuario interactúa para ingresar o visualizar datos. </p>

<table>
  <thead>
    <tr>
      <th>Categoría</th>
      <th>Ejemplo de Control en Flet</th>
      <th>Uso Principal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Entrada</strong></td>
      <td><code>ft.TextField</code></td>
      <td>Capturar texto o números del usuario.</td>
    </tr>
    <tr>
      <td><strong>Selección</strong></td>
      <td><code>ft.Dropdown</code> o <code>ft.Checkbox</code></td>
      <td>Elegir opciones de una lista.</td>
    </tr>
    <tr>
      <td><strong>Acción</strong></td>
      <td><code>ft.FloatingActionButton</code></td>
      <td>El botón principal de acción (el "+" flotante).</td>
    </tr>
    <tr>
      <td><strong>Visualización</strong></td>
      <td><code>ft.LineChart</code></td>
      <td>Mostrar datos y tendencias mediante gráficas.</td>
    </tr>
  </tbody>
</table>

</body>
<section>
  <h2>Bibliografía</h2>

  <ul>
    <li>
    <cite>Desarrollando una pequeña aplicación con Flet</cite>.
      (n.d.). Blog De Python Perú.
      <a href="https://blog.python.pe/blog/desarrollo-app-con-flet/" target="_blank">
        https://blog.python.pe/blog/desarrollo-app-con-flet/
      </a>
    </li>
    <li>
      Flet. (n.d.).
      <cite>Introduction - Flet</cite>.
      <a href="https://docs.flet.dev/" target="_blank">
        https://docs.flet.dev/
      </a>
    </li>
    <li>
      <cite>Fitzpatrick, M. (2025, December 13).
      <cite>First steps with the FLET Library for desktop and web GUI development</cite>.
      Python GUIs.
      <a href="https://www.pythonguis.com/tutorials/getting-started-flet/" target="_blank">
        https://www.pythonguis.com/tutorials/getting-started-flet/
      </a>
    </li>
    <li>
      <cite>Montes, K. F. R. (2024, November 19).
      <cite>Aprendiendo sobre Flet</cite>.
      <a href="https://es.linkedin.com/pulse/aprendiendo-sobre-flet-klint-fitzgerald-rom%C3%A1n-xw6ce" target="_blank">
        https://es.linkedin.com/pulse/aprendiendo-sobre-flet-klint-fitzgerald-rom%C3%A1n-xw6ce
      </a>
    </li>
  </ul>
</section>


