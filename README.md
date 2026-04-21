# trabajo-po-
PARTE 1: Análisis Teórico y Reflexión

1. Rastro de mensajes desde el main

El proceso arranca desde el objeto administración, que es el encargado de iniciar la acción. Desde ahí se llama a un método como imprimirPropietarios(), cuyo objetivo es mostrar la información.

Este objeto no trabaja de forma aislada, sino que delega responsabilidades. Primero le pide a cada Propietario que muestre sus datos; luego, el propietario consulta a su Propiedad, y esta, si lo necesita, obtiene información del CuartoUtil.

Visto de forma general, el flujo de mensajes sería:
Main → Administracion → Propietario → Propiedad → CuartoUtil.

⸻

2. Navegación y Gestión de Memoria

Para acceder desde un Propietario a su Propiedad, se utiliza un método como getPropiedad(), que retorna un puntero (Propiedad*). Por eso se usa el operador -> al momento de invocar métodos.

También es posible encadenar varias llamadas seguidas. Por ejemplo, para verificar si un cuarto útil está terminado, se puede usar:
propietario->getPropiedad()->getCuartoUtil()->isEstaTerminado().

En cuanto a la memoria, el uso de new implica que se está reservando memoria dinámicamente, por lo que es obligatorio liberarla después con delete. Si no se hace, esa memoria queda ocupada innecesariamente, generando lo que se conoce como una fuga de memoria (memory leak).
