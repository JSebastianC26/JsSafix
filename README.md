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
