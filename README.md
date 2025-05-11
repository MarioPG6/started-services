# Objetivo  
Este proyecto tiene como objetivo aplicar los fundamentos del ciclo de vida de los servicios en Android, específicamente los *Started Services*. Se busca implementar una aplicación que permita al usuario iniciar y utilizar un servicio desde una actividad, comprendiendo así el flujo de ejecución de un servicio y su interacción con la interfaz de usuario.

# Presentación  
El desarrollo se basa en el laboratorio **"Convergentes - Started Services"**, donde se crea una aplicación Android que lanza un servicio llamado `DelayedMessageService` desde `MainActivity`. Este servicio simula una operación de retardo y luego genera una notificación. Además, se incluye una funcionalidad adicional: el envío de notificaciones personalizadas para eventos del proyecto como reservas o cumplimiento de paseos.

# Desarrollo  
## Aspectos Clave Trabajados

### Diseño de la Interfaz de Usuario:
- Creación de `activity_main.xml` con un `TextView` y un `Button` para iniciar el servicio.
- El botón activa el servicio y también simula el envío de una notificación inmediata relacionada con una reserva de paseo.

### Manejo de Recursos:
- Uso de `strings.xml` para definir los textos de botones, mensajes y títulos de notificaciones.
- Manejo ordenado de recursos para facilitar localización y mantenimiento.

### Lógica de Negocio:
- Implementación de `DelayedMessageService`, una clase que extiende `IntentService`:
  - Usa `onHandleIntent()` para simular una operación que toma tiempo.
  - Luego muestra una notificación con un mensaje recibido desde `MainActivity`.
- Se creó una clase utilitaria `NotificationHelper` que permite enviar notificaciones personalizadas desde cualquier parte de la app.
- Las notificaciones utilizan canales (`NotificationChannel`) compatibles con Android 8+.

### Conexión entre la Interfaz y la Lógica:
- `MainActivity` inicia el servicio con `startService()` al pulsar un botón.
- También utiliza `NotificationHelper` para mostrar notificaciones personalizadas de eventos simulados como "Reserva de Paseo".
- Se implementa una solicitud de permiso para `POST_NOTIFICATIONS` en Android 13+.

## Ejemplo de Funcionamiento
1. El usuario abre la app y presiona el botón “¿Cuál es tu chiste?” (puede personalizarse como “Iniciar Paseo”).
2. La app envía una notificación inmediata de tipo "Nueva Reserva de Paseo".
3. Luego de unos segundos, el `DelayedMessageService` lanza otra notificación simulando un mensaje demorado.

## Imágenes de Funcionamiento
![image](https://github.com/user-attachments/assets/5e4b128b-b9e5-4d67-9e6d-20f1d2657e88)
![image](https://github.com/user-attachments/assets/4634c234-95b2-42f4-ae49-e7cb3c6caa36)

# Conclusión  
Este proyecto demostró la aplicación práctica de servicios iniciados (*started services*) en Android, incluyendo el ciclo de vida del servicio, uso de `IntentService`, envío de datos mediante `Intent`, creación de notificaciones y el uso de canales. También se integraron buenas prácticas como la solicitud dinámica de permisos y la reutilización de lógica para notificaciones mediante una clase helper.

# Referencias  
- Head First Android Development de Dawn Griffiths y David Griffiths, O’Reilly Media, Inc.  
- Presentación de apoyo: **"Convergentes - Started Services"**
