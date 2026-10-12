# Toto Barber — Página de turnos

Esta carpeta contiene la página web de Tomás Oviedo — Barbería · Turnos.

## Publicar la página en GitHub Pages

1. Entrá a GitHub e iniciá sesión.
2. Creá un repositorio nuevo, por ejemplo `toto-barber`.
3. Subí **todos los archivos de esta carpeta** (especialmente `index.html`).
4. En el repositorio, entrá a **Settings → Pages**.
5. En **Build and deployment**, elegí **Deploy from a branch**.
6. Elegí la rama `main` y la carpeta `/ (root)`, y guardá.
7. Esperá a que GitHub publique la web. La dirección aparecerá en esa misma sección.

## Importante: conexión con Firebase

El `index.html` intenta conectarse a Firebase para compartir los turnos entre los clientes y el administrador. Publicar el archivo en GitHub **no crea ni configura la base de datos automáticamente**.

Antes de usar la página en público, verificá en Firebase Console que el proyecto `toto-barber` exista y que estén configurados:

- Authentication: acceso anónimo habilitado para los visitantes.
- Authentication: proveedor **Correo electrónico/Contraseña** habilitado para el administrador.
- Firestore Database: base de datos creada.
- Documento `admins/{UID_DEL_ADMIN}`: debe existir para el usuario administrador que inicia sesión.
- Reglas de Firestore adecuadas para el funcionamiento de la aplicación.

### Aviso de privacidad y seguridad

La versión actual guarda el nombre del cliente y el servicio en los documentos de turnos. No publiques la página como lista para uso real hasta revisar las reglas y la estructura de Firestore: si se permite leer públicamente toda la colección `bookings`, otras personas podrían consultar esos datos aunque la interfaz solo muestre “Ocupado”. Lo ideal es separar la disponibilidad pública de los datos privados de los clientes.

## Horarios incluidos

- Lunes: 18:00–21:00
- Martes: 14:00–21:00
- Miércoles: 15:00–21:00
- Jueves a sábado: 14:00–21:00
- Domingo: cerrado

Los turnos son de una hora, tal como están definidos en el código.
