# Visualizador Branch & Bound y Método Simplex

Este proyecto contiene herramientas visuales para el aprendizaje de métodos de optimización en Investigación de Operaciones:

- **Visualizador Branch & Bound**: Herramienta interactiva para visualizar el algoritmo Branch & Bound en problemas de programación entera.
- **Método Simplex**: Implementación del método simplex (usando Big M) con visualización de tableaus paso a paso.

## Características

### Visualizador Branch & Bound

- Visualización gráfica del árbol de decisión
- Seguimiento paso a paso del algoritmo
- Interacción con nodos (zoom, desplazamiento, información detallada)
- Soporte para múltiples problemas predefinidos
- Visualización de estados (solución entera, fraccionaria, podas por cota e infactibilidad)

### Método Simplex

- Implementación completa del método Simplex usando Big M
- Visualización de tableaus en cada iteración
- Destacado de elementos pivote y valores significativos
- Interpretación de resultados finales
- Diseño responsivo y estéticamente agradable

## Tecnologías Utilizadas

- React 19
- JavaScript moderno
- JavaScript LP-Solver (para resolver problemas lineales)
- Vite (entorno de desarrollo)
- CSS personalizado

## Estructura del Proyecto

- `/src/components/BnbVisualizer.jsx`: Componente principal del visualizador Branch & Bound
- `/src/components/SimplexSolver.jsx`: Componente del método Simplex
- `/src/components/Modal.jsx`: Componente modal para mostrar detalles de nodos
- `/src/components/*.css`: Archivos de estilos para los componentes

## Instalación y Ejecución

**Requisitos previos:**
- Node.js (v18 o superior recomendado)
- npm (generalmente viene con Node.js)

**Pasos:**

1. **Clonar el repositorio:**
   Abre tu terminal o línea de comandos y ejecuta:
   ```bash
   git clone <url-del-repositorio>
   ```
   (Reemplaza `<url-del-repositorio>` con la URL real del repositorio Git).

2. **Navegar al directorio del proyecto:**
   ```bash
   cd bnb-visualizer
   ```

3. **Instalar dependencias:**
   Ejecuta el siguiente comando para instalar todas las librerías necesarias:
   ```bash
   npm install
   ```

4. **Ejecutar el servidor de desarrollo:**
   Para iniciar la aplicación en modo de desarrollo, usa:
   ```bash
   npm run dev
   ```
   Este comando compilará el proyecto y lo servirá localmente.

5. **Abrir en el navegador:**
   Una vez que el servidor esté corriendo (verás un mensaje en la terminal, usualmente indicando `Local: http://localhost:xxxx/`), abre tu navegador web y ve a:
   ```
   http://localhost:5173/
   ```
   (El puerto `5173` es el predeterminado para Vite, pero podría ser diferente si está ocupado. Revisa la salida de la terminal).

## Uso

### Visualizador Branch & Bound
1. Selecciona un problema del menú desplegable
2. Haz clic en "Inicializar y Resolver Nodo Raíz"
3. Utiliza "Siguiente Iteración" para avanzar paso a paso
4. Haz clic en cualquier nodo para ver detalles
5. Usa el mouse para:
   - **Desplazar el árbol**: Mantén presionado y arrastra
   - **Zoom**: Utiliza la rueda del mouse
   - **Ver detalles**: Clic en cualquier nodo

### Método Simplex
1. Navega a la pestaña o sección del Método Simplex
2. Revisa el problema de inversión tecnológica presentado
3. Haz clic en "Mostrar Iteraciones" para ver los tableaus
4. Navega por las iteraciones con los botones "Anterior" y "Siguiente"
5. Observa la interpretación de resultados al final de la página

## Personalización

Para añadir nuevos problemas al visualizador Branch & Bound, modifica el array `problemBank` en el archivo:
```javascript
// BnbVisualizer.jsx
const problemBank = [
  {
    name: "Nombre del Problema", 
    optimize: "Z",
    opType: "max", // o "min" para minimización
    constraints: { /* restricciones */ },
    variables: { /* variables con coeficientes */ },
    variableNames: ["x1", "x2", /*...*/]
  },
  // Añade más problemas aquí
];
```

Para el componente Simplex, modifica el objeto `model` en:
```javascript
// SimplexSolver.jsx
const model = {
  optimize: "cost", 
  opType: "min",
  constraints: { /* restricciones */ },
  variables: { /* variables con coeficientes */ }
};
```

## Scripts Disponibles

- **Desarrollo:** `npm run dev` - Inicia el servidor de desarrollo
- **Construir:** `npm run build` - Genera una versión de producción en la carpeta `/dist`
- **Vista previa:** `npm run preview` - Muestra la versión de producción localmente
- **Linting:** `npm run lint` - Ejecuta el linter para encontrar problemas

## Licencia

Este proyecto está licenciado bajo la Licencia MIT - consulta el archivo [LICENSE](LICENSE) para más detalles.

## Colaboración

Las contribuciones son bienvenidas. Por favor:

1. Haz un Fork del repositorio
2. Crea una rama para tu funcionalidad (`git checkout -b feature/nueva-funcionalidad`)
3. Realiza tus cambios y haz commit (`git commit -m 'Añade nueva funcionalidad'`)
4. Sube los cambios a tu rama (`git push origin feature/nueva-funcionalidad`)
5. Abre un Pull Request

## Contacto

Para preguntas o comentarios sobre este proyecto, puedes contactar al mantenedor del repositorio.

---

Desarrollado para el curso de Investigación de Operaciones - Programación Entera
