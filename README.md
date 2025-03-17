# Manual de Uso - Módulo Safix

## Descripción General
El módulo `safix.js` es una biblioteca de utilidades diseñada para facilitar el desarrollo de aplicaciones web en el entorno Safix. Este módulo proporciona funciones comunes y configuraciones que pueden ser utilizadas en toda la aplicación.

## Funciones Principales

### 1. nvl(valorPrincipal, valorReemplaza)
Función para manejar valores nulos o indefinidos.
```javascript
// Ejemplo de uso:
const valor = safix.nvl(null, "valor por defecto"); // retorna "valor por defecto"
const valor2 = safix.nvl("valor existente", "valor por defecto"); // retorna "valor existente"
```

### 2. esDispositivoMovil()
Detecta si la aplicación está siendo accedida desde un dispositivo móvil.
```javascript
// Ejemplo de uso:
if (safix.esDispositivoMovil()) {
    // Código para dispositivos móviles
}
```

## Constantes y Configuraciones

### Colores
El módulo incluye dos paletas de colores predefinidas:

#### Colores Estándar
```javascript
safix.colores = {
    VA_ROJO: "#ff0000",
    VA_NARANAJA: "#ff7300",
    VA_AZUL: "#0509fa",
    VA_VERDE: "#00ff00",
    VA_AMARILLO: "#ffff00",
    VA_BLANCO: "#ffffff",
    VA_GRIS: "#b8b4b4",
    VA_GRIS_OSCURO: "#5a5a5a"
}
```

#### Colores Pastel
```javascript
safix.coloresPastel = {
    VA_ROJO: "#FADBD8",
    VA_NARANAJA: "#ffe8d8",
    VA_AZUL: "#dde8f9",
    VA_VERDE: "#d2ebd2",
    VA_AMARILLO: "#FCF3CF"
}
```

### Configuración IndexDB
```javascript
safix.IndexDB = {
    NombreBD: "IndexDB - Safix",
    DataIndex: "DmlPorEnviar",
    Usuarios: "Users",
    Terminal: "DatosTerminal"
}
```

### Variables PWA
Configuración para Progressive Web App (PWA):
```javascript
safix.VariablesPwa = {
    url_service_worker: "/sw_safix.js",
    // Las rutas se configuran automáticamente basadas en la URL actual
}
```

## Características Especiales

### Seguimiento del Último Elemento Enfocado
El módulo mantiene un registro del último elemento que recibió el foco:
```javascript
// El último elemento enfocado se puede acceder mediante:
safix.ultimoItemFocus
```

## Buenas Prácticas

1. **Nomenclatura**: Se recomienda usar nombres en español para mantener la consistencia con el módulo.
2. **Programación Orientada a Objetos**: Todo el código debe estar encapsulado dentro de módulos.
3. **Documentación**: Mantener la documentación actualizada para cada nueva función o característica.

## Compatibilidad
- El módulo está diseñado para funcionar tanto en dispositivos móviles como en computadoras de escritorio.
- Se incluye detección automática del tipo de dispositivo.

## Historial de Cambios
- Mayo 05 2023: Creación inicial del archivo global (Johan Cardona)
- Mayo 06 2023: Adición de módulo para ejecución de eventos (Sramirez)
- Febrero 14 2025: Modificación de función para último item con focus (Johan Cardona) 


# Módulo safix.procesos.js

## Descripción
Este módulo contiene una colección de funciones reutilizables para el manejo de procesos en la aplicación. Fue creado por Johan Cardona y ha sido actualizado en varias ocasiones, incluyendo la última actualización en marzo de 2025.

## Historial de Cambios
- Mayo 05 2023: Creación inicial del módulo de funciones reutilizables
- Feb 14 2025: Agregada función para control de enfoque en los items
- Mar 07 2025: Agregadas nuevas funciones para manejo de estilos y control de elementos

## Estructura del Módulo

### Listas Reutilizables (`procesos.listas`)

#### tiposEnmascaramientos
```javascript
{
    "$": "pesos",
    "€": "euros",
    "D": "dolares",
    "#": "ninguno",
    "P": "ninguno"
}
```

#### regionesMoneda
```javascript
{
    dolares: "en-US",
    pesos: "es-CO",
    euros: "es-ES"
}
```

#### monedas
```javascript
{
    dolares: "USD",
    pesos: "COP",
    euros: "EUR"
}
```

## Funciones Principales

### 1. ObtenerMascara
```javascript
procesos.obtenerMascara(tipoMascara)
```
Obtiene el tipo de máscara que se va a aplicar.
- **Parámetros:**
  - `tipoMascara`: Tipo de máscara requerida (dolares, pesos, etc.)
- **Retorna:** Objeto JSON con la máscara

### 2. EnmascararValores
```javascript
procesos.EnmascararValores(region, moneda, pValor)
```
Enmascara valores numéricos según la región y moneda especificadas.
- **Parámetros:**
  - `region`: Región del intercambio de moneda
  - `moneda`: Tipo de moneda
  - `pValor`: Valor a convertir

### 3. ArmarParametrosX01
```javascript
procesos.ArmarParametrosX01()
```
Obtiene todos los valores de los items de una página.
- **Retorna:** JSON string con key = Nombre del campo, Value = Su valor

### 4. datosGridFilaSeleccionada
```javascript
procesos.datosGridFilaSeleccionada()
```
Arma JSON con los datos de un grid en la fila seleccionada.
- **Retorna:** Objeto con los datos de la fila seleccionada

### 5. Redirecionamiento
```javascript
procesos.redirecionamiento(TipoLink, link)
```
Función para redireccionar a otras páginas modales o normales.
- **Parámetros:**
  - `TipoLink`: Tipo de página destino ("MODAL" o "NORMAL")
  - `link`: Link destino

### 6. Control de Formularios
- `procesos.limpiarFormulario()`: Limpia formularios
- `procesos.desabilitarItem(item)`: Deshabilita items
- `procesos.habilitarItems(item)`: Habilita items
- `procesos.pintarItem(item, color)`: Pinta items de un formulario

### 7. Hipervínculos
```javascript
procesos.hipervinculos(idItem)
```
Funcionalidad de hipervínculos para diferentes templates configurados.
- **Parámetros:**
  - `idItem`: ID del item o del hipervínculo

### 8. Asignaciones
- `procesos.asignaciones(res)`: Asigna valores a todos los items de una página
- `procesos.asignaciones2(res)`: Asigna valores sin ejecutar acción dinámica

### 9. Utilidades
- `procesos.mensajesConsola`: Manejo de consola configurable
- `procesos.xml_To_Json(DataXml)`: Conversión de XML a JSON
- `procesos.mostrarRegion(idRegion)`: Refresca y muestra regiones
- `procesos.tomarItemsNoNulos()`: Arma JSON string con items no nulos
- `procesos.listarInputsVisibles()`: Retorna items visibles en pantalla
- `procesos.recuperarEnfoque()`: Recupera el enfoque en items nulos

### 10. Control de Estilos
```javascript
procesos.insertarEstiloPersonalizado(idObjetivo, textoContenido, opciones)
```
Inserta reglas de estilo personalizadas.
- **Parámetros:**
  - `idObjetivo`: ID del elemento
  - `textoContenido`: Texto a mostrar
  - `opciones`: Configuración adicional de estilos

### 11. Control de Elementos
```javascript
procesos.controlarElemento(idElemento, inhabilitar, opciones)
```
Inhabilita o habilita elementos de entrada con estilos personalizados.
- **Parámetros:**
  - `idElemento`: ID del elemento
  - `inhabilitar`: Boolean para inhabilitar/habilitar
  - `opciones`: Configuración visual adicional

## Uso
```javascript
// Ejemplo de uso básico
safix.procesos.EnmascararValores('es-CO', 'COP', 1234567898);

// Ejemplo de control de elemento
const control = safix.procesos.controlarElemento('miElemento', true, {
    colorTexto: '#000000',
    colorFondo: '#f0f0f0'
});
```

## Notas
- El módulo utiliza jQuery para algunas operaciones
- Requiere la existencia de variables globales como `paginaActual` y `aplicacionActual`
- Incluye manejo de errores y logging configurable
- Soporta internacionalización para diferentes monedas y regiones 
