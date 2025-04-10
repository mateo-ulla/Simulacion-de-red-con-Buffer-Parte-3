# Simulación de Red (PARTE 3) en Python

Este proyecto es una simulación básica de una red de comunicación implementada en Python utilizando **Programación Orientada a Objetos (POO)**. Se modela la comunicación entre un **servidor** y **tres clientes**, permitiendo la transmisión de mensajes entre ellos, además de simular la pérdida de paquetes y la reconexión dinámica de nodos.

## Características

- Implementa la clase `Nodo`, que representa un dispositivo en la red.
- Permite conectar y desconectar nodos dinámicamente.
- Simula el envío y recepción de mensajes entre nodos conectados.
- Simula pérdida de paquetes con una probabilidad del 30%.
- Permite envío de mensajes de broadcast o específicos.
- Uso de `time.sleep()` para representar retrasos en la red y reconexiones.

## Explicación del Código

### 1. **Clase `Nodo`**

Cada nodo en la red tiene:
- Un `nombre` que lo identifica.
- Una lista `conexiones` para almacenar los nodos conectados.

### 2. **Métodos de la Clase `Nodo`**

- `agregar_conexion(nodo)`: Conecta el nodo con otro.
- `eliminar_conexion(nodo)`: Desconecta el nodo de otro.
- `procesar_buffer(nodo, mensaje)`: Simula el envío de un mensaje a un nodo, con posibilidad de pérdida.
- `enviar_mensaje(mensaje)`: Envía un mensaje a todos los nodos conectados.
- `recibir_mensaje(mensaje, emisor)`: Recibe un mensaje y muestra el emisor.

### 3. **Flujo del Programa**

1. Se crean un servidor y tres clientes.
2. El servidor se conecta inicialmente a los tres clientes.
3. El servidor envía un mensaje de broadcast a todos los clientes conectados.
4. Se simula la desconexión del Cliente 2.
5. Después de una pausa de 2 segundos, se reconecta al Cliente 2.
6. Se envía un nuevo mensaje a todos los clientes (incluyendo el recién reconectado).
7. Se envía un mensaje directo desde el servidor a Cliente 3.

### 4. **Simulación de Pérdida de Paquetes**

Durante la transmisión, existe una probabilidad del 30% de que un paquete se pierda. En ese caso, el mensaje no llegará a destino y se imprime un aviso.
