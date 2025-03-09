# ⏳ Recordatorio Automático: "¡Bebe Agua Cada Hora!"  

Este tutorial explica cómo programar un recordatorio automático que te avise cada hora con el mensaje **"¡Bebe agua!"**.  
Las instrucciones están disponibles para **Linux/macOS** y **Windows**.  

---

## 🐧 Para Usuarios de Linux (Cron Jobs)

### 📌 ¿Qué es Cron?  
Cron es una herramienta en Linux/macOS que permite programar tareas automáticas en intervalos específicos, como minutos, horas o días.  

### 🛠️ **Pasos para Crear un Cron Job**  

1️⃣ Abrir la terminal** (`Ctrl + Alt + T`).
2️⃣ Editar la lista de cron jobs con el comando:  
```sh
crontab -e
```
3️⃣ Agregar la siguiente línea al final del archivo:
```sh
0 * * * * echo "¡Bebe agua!" >> ~/recordatorio.txt
```
📖 Explicación:
```sh
0 * * * * → Se ejecuta en el minuto 0 de cada hora.
```
4️⃣ Guardar y salir:

Si usaste nano, presiona CTRL + X, luego Y, y Enter.
5️⃣ Verificar los cron jobs activos con:
```sh
crontab -l
```

## 🖥️ Para Usuarios de Windows (Task Scheduler)
### 📌 ¿Qué es el Programador de Tareas?
El **Programador de Tareas (Task Scheduler)** es una herramienta de Windows que permite ejecutar acciones automáticamente en momentos programados.

### 🛠️ **Pasos para Crear una Tarea Programada**
1️⃣ Abrir el Programador de Tareas
- Presiona Win + R, escribe taskschd.msc y presiona Enter.
- En el panel derecho, haz clic en Crear Tarea Básica.

2️⃣ Configurar la tarea
- Nombre: Recordatorio Agua
- Descripción: "Muestra un recordatorio cada hora para beber agua".

3️⃣ Configurar el desencadenador (Trigger)
- Selecciona Diariamente y presiona Siguiente.
- Configura la hora inicial (ejemplo: 09:00 AM).Activa la opción Repetir cada 1 hora durante 1 día.

4️⃣ Configurar la acción
- Selecciona Iniciar un programa y presiona Siguiente.
- En Programa o script, escribe:
```powershell
powershell.exe
```
- En agregar argumentos
```powershell
[System.Windows.MessageBox]::Show("¡Bebe agua!")
```
- Esto mostrará un mensaje emergente en pantalla cada hora.

5️⃣ Finalizar y probar
- Haz clic en Finalizar y busca la tarea en la lista.
- Haz clic derecho en Recordatorio Agua y selecciona Ejecutar para probarla.