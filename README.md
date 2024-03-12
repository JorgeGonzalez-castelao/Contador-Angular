## Contador en Angular

Este proyecto te guiará a través del proceso de creación de un contador simple utilizando Angular. El contador tendrá la funcionalidad de incrementar y decrementar un número.

### Requisitos

Antes de comenzar, asegúrate de tener instalado Angular CLI en tu sistema. Si no lo tienes, puedes instalarlo ejecutando el siguiente comando en tu terminal:

```bash
npm install -g @angular/cli
```

### Crear un Nuevo Proyecto Angular

Primero, crea un nuevo proyecto Angular ejecutando:

```bash
ng new contador-app
```

Luego, ingresa al directorio del proyecto:

```bash
cd contador-app
```

### Crear el Componente del Contador

Para el contador, vamos a crear un nuevo componente. Ejecuta el siguiente comando para generar el componente del contador:

```bash
ng generate component contador
```

### Implementar la Lógica del Contador

Abre el archivo `home.component.ts` en el directorio `src/app/home/` y agrega el siguiente código para implementar la lógica del contador:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.css']
})
export class ContadorComponent {
  contador: number = 0;

  incrementar() {
    this.contador++;
  }

  decrementar() {
    if (this.contador > 0) {
      this.contador--;
    }
  }
}
```

### Crear la Interfaz del Usuario

Abre el archivo `home.component.html` y agrega el siguiente código para definir la interfaz de usuario del contador:

```html
<div class="contador-container">
  <div class="botones-container">
    <button class="contador-button" (click)="incrementar()">Incrementar</button>
    <span class="contador-value">{{ contador }}</span>
    <button class="contador-button" (click)="decrementar()">Decrementar</button>
  </div>
</div>
```

### Integrar un estilo

en home.component.css añadir un estilo para nuestro programa, esto ya es peronal para cada usuario:

```css
/* contador.component.css */

/* Estilos para el contenedor del contador */
.contador-container {
  display: flex;
  justify-content: space-around; /* Ajusta el espacio entre los elementos */
  align-items: center;
  font-family: Arial, sans-serif;
}

/* Estilos para el contenedor de los botones */
.botones-container {
  border: 2px solid #007bff; /* Añade un borde estilizado */
  border-radius: 10px; /* Redondea las esquinas */
  overflow: hidden; /* Evita que los botones sobrepasen el borde */
  padding: 5px; /* Añade espacio entre el borde y los botones */
}

/* Estilos para los botones */
.contador-button {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  background-color: #007bff;
  color: #fff;
  cursor: pointer;
  border-radius: 0; /* Quita el borde redondeado de los botones internos */
  transition: background-color 0.3s ease;
}

/* Estilos cuando se pasa el ratón sobre los botones */
.contador-button:hover {
  background-color: #0056b3;
}

/* Estilos para el valor del contador */
.contador-value {
  font-size: 24px;
  margin: 0 10px; /* Añade margen entre el valor del contador y los botones */
}

/* Estilos para dispositivos móviles */
@media (max-width: 768px) {
  .contador-container {
    flex-direction: column;
    align-items: center; /* Centra los elementos en dispositivos móviles */
  }

  .contador-button {
    margin-top: 10px; /* Agrega espacio entre los botones en dispositivos móviles */
  }
}

```




### Integrar el Componente del Contador

Por último, agrega el componente `app-contador` al template del componente principal, generalmente ubicado en `app.component.html`, así:

```html
<h1>Contador App</h1>
<app-contador></app-contador>
```

### Ejecutar la Aplicación

Ahora, ejecuta tu aplicación Angular con `ng serve` y abre tu navegador web. Navega a `http://localhost:4200/` para ver la aplicación en acción. Puedes incrementar y decrementar el contador haciendo clic en los botones correspondientes.


