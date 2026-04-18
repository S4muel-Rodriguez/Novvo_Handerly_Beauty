# Configuración de Google OAuth - NOVVO Handerly Beauty

## � SOLUCIÓN RÁPIDA - Sin Google OAuth (Por ahora)

Tu sitio **ya está funcionando** con credenciales de prueba:

```
Email: prueba@novvo.com
Contraseña: Novvo123
```

Puedes iniciar sesión inmediatamente y probar todas las funcionalidades incluyendo:
- ✓ Fotos de perfil
- ✓ Testimonios
- ✓ Consultas

---

## 📱 ¿Qué es Google OAuth?
Google OAuth permite que los usuarios inicien sesión usando su cuenta de Google. Esto automáticamente captura: nombre, email y **foto de perfil**.

---

## 🔧 Paso a Paso para Configurar Google OAuth (OPCIONAL)

Si prefieres agregar Google Sign-In real, sigue estos pasos:

### Paso 1: Crear un Proyecto en Google Cloud Console
1. Ve a https://console.cloud.google.com
2. Haz clic en el menú desplegable de proyectos (arriba a la izquierda)
3. Haz clic en "NUEVO PROYECTO"
4. Dale un nombre (ej: "NOVVO Handerly Beauty")
5. Haz clic en "CREAR"

### Paso 2: Habilitar la API de Google+
1. Espera a que se cree el proyecto
2. En la barra de búsqueda, escribe "Google+ API"
3. Haz clic en "Google+ API"
4. Haz clic en el botón "HABILITAR"

### Paso 3: Crear Credenciales OAuth
1. En el menú izquierdo, ve a "Credenciales"
2. Haz clic en "Crear credenciales" (botón azul)
3. Selecciona "ID de cliente OAuth"
4. Si te pide configurar la pantalla de consentimiento, haz clic en "Configurar pantalla de consentimiento"

### Paso 4: Configurar la Pantalla de Consentimiento
1. Selecciona "Externo"
2. Haz clic en "CREAR"
3. Completa la información:
   - **Nombre de la aplicación:** NOVVO Handerly Beauty
   - **Email de soporte:** novvohanderlybeauty@gmail.com
   - Sigue hasta el final
4. Haz clic en "GUARDAR Y CONTINUAR" repetidamente hasta volver al panel

### Paso 5: Crear las Credenciales
1. De nuevo en "Credenciales", haz clic en "Crear credenciales"
2. Selecciona "ID de cliente OAuth"
3. Selecciona **"Aplicación web"** como tipo de aplicación
4. Dale un nombre (ej: "NOVVO Web")
5. En "URIs autorizados de JavaScript":
   - Haz clic en "Agregar URI"
   - Añade: `http://localhost:3000` (para pruebas locales)
   - Haz clic en "Agregar URI"
   - Añade: `https://tudominio.com` (cuando tengas un dominio)
6. En "URIs autorizados de redireccionamiento":
   - Haz clic en "Agregar URI"
   - Añade: `http://localhost:3000` (para pruebas locales)
7. Haz clic en "CREAR"

### Paso 6: Copiar tu Client ID
1. Verás una ventana emergente con tu "Client ID"
2. **COPIA TODO EL CLIENT ID** 
   - Ejemplo: `123456789-abcdefgh.apps.googleusercontent.com`
3. Cierra la ventana

### Paso 7: Actualizar el HTML
1. Abre el archivo `NOVVO_Premium_Profesional.html`
2. Busca esta línea (aproximadamente en la línea 2180):

```javascript
const CLIENT_ID = '1234567890-abcdefghijklmnopqrstuvwxyz.apps.googleusercontent.com';
```

3. Reemplaza `1234567890-abcdefghijklmnopqrstuvwxyz.apps.googleusercontent.com` con tu Client ID real:

```javascript
const CLIENT_ID = '123456789-abcdefgh.apps.googleusercontent.com';
```

4. Guarda el archivo
5. Actualiza el navegador
6. ¡Ahora funciona Google OAuth!

---

## ✅ Verificación

Después de configurar Google OAuth, deberías ver:
- ✓ Un botón azul de Google en el modal de login
- ✓ Al hacer clic, se abre una ventana de Google
- ✓ Después de autenticarse, la foto de perfil aparece en el header
- ✓ Los testimonios muestran la foto del usuario

---

## 🔐 Notas de Seguridad
- El Client ID es público y seguro compartirlo
- Nunca comparta el "Client Secret" en código público
- Google OAuth verifica automáticamente la identidad
- Las fotos vienen directamente de Google (seguras)

---

## ❓ Solución de Problemas

### "Error: popup closed by user"
El usuario cerró la ventana de Google sin completar el login. Es normal, intenta de nuevo.

### "Error: The origin is not authorized"
Tu dominio no está registrado. Agrega tu dominio en "URIs autorizados de JavaScript" en Google Cloud Console.

### "Error 404"
Estás usando el Client ID placeholder. Sigue los pasos 1-7 arriba.

### Las fotos no aparecen
Verifica que:
- El usuario haya iniciado sesión con Google
- Google tenga permiso para compartir foto de perfil

---

## 📞 Necesitas Ayuda?

Contacta al equipo NOVVO Handerly Beauty.

---

## 🎯 Estado Actual

**Para DESARROLLO/PRUEBAS:** Usa `prueba@novvo.com` / `Novvo123`

**Para PRODUCCIÓN:** Configura Google OAuth siguiendo los pasos arriba

