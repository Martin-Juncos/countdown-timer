Aquí tienes un archivo `README.md` para el proyecto "countdown-timer" de Martin Juncos:

```markdown
# Proyecto de Temporizador de Cuenta Regresiva en JavaScript

### Descripción del Proyecto

Este proyecto es una implementación de un temporizador de cuenta regresiva utilizando JavaScript. Permite a los usuarios establecer una fecha objetivo y muestra el tiempo restante hasta esa fecha en días, horas, minutos y segundos.

### Lógica del Código

El proyecto utiliza JavaScript para calcular el tiempo restante hasta la fecha objetivo y actualizar la interfaz de usuario en tiempo real. A continuación, se describe la lógica principal del código:

1. **Configuración Inicial**:
   Se define una fecha objetivo (`targetDate`) hacia la cual el temporizador cuenta regresivamente. Esta fecha se puede modificar según las necesidades del usuario.
   ```javascript
   const targetDate = new Date('Dec 31, 2024 23:59:59').getTime();
   ```

2. **Cálculo del Tiempo Restante**:
   Se calcula el tiempo restante comparando la fecha actual con la fecha objetivo. Esto se hace dentro de una función que se ejecuta cada segundo utilizando `setInterval`.
   ```javascript
   const interval = setInterval(() => {
     const now = new Date().getTime();
     const distance = targetDate - now;
   }, 1000);
   ```

3. **Conversión del Tiempo**:
   El tiempo restante se convierte en días, horas, minutos y segundos.
   ```javascript
   const days = Math.floor(distance / (1000 * 60 * 60 * 24));
   const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
   const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
   const seconds = Math.floor((distance % (1000 * 60)) / 1000);
   ```

4. **Actualización de la Interfaz de Usuario**:
   Los valores calculados se muestran en la interfaz de usuario actualizando el contenido de elementos HTML específicos.
   ```javascript
   document.getElementById('days').innerText = days;
   document.getElementById('hours').innerText = hours;
   document.getElementById('minutes').innerText = minutes;
   document.getElementById('seconds').innerText = seconds;
   ```

5. **Finalización del Temporizador**:
   Cuando se alcanza la fecha objetivo, se detiene el temporizador y se puede mostrar un mensaje indicando que el tiempo ha terminado.
   ```javascript
   if (distance < 0) {
     clearInterval(interval);
     document.getElementById('countdown').innerText = '¡Tiempo terminado!';
   }
   ```

### Uso del Temporizador de Cuenta Regresiva

1. **Abrir el Archivo**:
   Abre el archivo `index.html` en tu navegador para ver el temporizador en acción.

2. **Establecer la Fecha Objetivo**:
   Modifica la variable `targetDate` en el archivo JavaScript para establecer tu propia fecha objetivo.

3. **Visualizar el Tiempo Restante**:
   El temporizador mostrará el tiempo restante en días, horas, minutos y segundos, actualizándose en tiempo real.

### Modificación del Temporizador

Para modificar el comportamiento del temporizador, puedes cambiar el código JavaScript. También puedes modificar el CSS y el HTML para cambiar la apariencia de la página y del temporizador.

                            ©ProfMartinJuncos
```
