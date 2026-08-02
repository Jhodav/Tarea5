# Tarea #5 - ESP32: UART, I2C y FreeRTOS

**Autor:** Jhony David Choez López  
**Plataforma:** Wokwi Online (ESP-IDF) /Platformio 
---

## 📝 Descripción General

Este repositorio contiene el desarrollo completo de la Tarea #5 de Sistemas Embebidos, compuesta por tres ejercicios prácticos que integran comunicación UART, multitarea con FreeRTOS y visualización en pantalla OLED mediante I2C, todo implementado sobre el microcontrolador ESP32 en el entorno Wokwi.

---

## Ejercicio 1 – Comunicación Serial Avanzada con UART2

**Descripción:**  
Aplicación que utiliza el puerto UART2 del ESP32 (pines GPIO17 para TX y GPIO16 para RX) para implementar un sistema de comandos seriales. Permite interactuar con el sistema mediante un terminal serial, ejecutando acciones internas y respondiendo con información estructurada.

**Comandos implementados:**  
- `status` → Muestra el estado actual del sistema y del LED.  
- `led on` / `led off` → Enciende o apaga el LED (GPIO2).  
- `info` → Muestra la velocidad de baudios y el contador de comandos.  
- `reset` → Reinicia las variables internas sin reiniciar el microcontrolador.

---

## Ejercicio 2 – Sistema Multitarea con FreeRTOS

**Descripción:**  
Diseño de un sistema multitarea que ejecuta tres tareas concurrentes utilizando FreeRTOS. Cada tarea tiene una prioridad y función específica, demostrando la capacidad del ESP32 para manejar múltiples procesos de manera eficiente.

**Tareas implementadas:**  
- **Tarea 1:** Lectura periódica de un sensor virtual (simulado con un temporizador).  
- **Tarea 2:** Control de un LED con diferente frecuencia de parpadeo.  
- **Tarea 3:** Envío periódico de información al monitor serial.

**Tecnologías usadas:**  
- `xTaskCreate()` para la creación de tareas.  
- `vTaskDelay()` para la temporización.  
- Prioridades diferentes para cada tarea.

---

## Ejercicio 3 – Sistema Integrado: UART + FreeRTOS + I2C

**Descripción:**  
Sistema completo que integra los ejercicios anteriores en una sola aplicación funcional. Procesa comandos UART, ejecuta múltiples tareas con FreeRTOS y visualiza un gráfico de tiempo en una pantalla OLED a través del bus I2C.

**Componentes integrados:**  
- **UART0 (GPIO1/3):** Recepción y procesamiento de comandos del usuario.  
- **FreeRTOS:** 3 tareas concurrentes (Procesador de comandos, Control de LED, Gráfico OLED).  
- **I2C (GPIO21/22):** Actualización de pantalla OLED SSD1306 con gráfico de actividad.  
- **LED (GPIO2):** Control mediante comandos `led on` / `led off`.

**Gráfico OLED:**  
Muestra un historial deslizante de la actividad de las tres tareas mediante barras horizontales y líneas punteadas como marcas de tiempo (T1, T2).

---
