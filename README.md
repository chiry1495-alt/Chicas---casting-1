# Chicas Casting — web inicial

Esta carpeta contiene una web de anuncios con portada pública y panel privado. Incluye una configuración inicial con Supabase para autenticación, base de datos y almacenamiento de imágenes.

## Antes de publicarla

- Está diseñada para anuncios profesionales dirigidos exclusivamente a mayores de 18 años.
- No subas imágenes de otra persona sin permiso expreso ni datos personales innecesarios.
- El correo de contacto debe ser una dirección que controles.
- Los anuncios de demostración de la portada aparecen si aún no has conectado Supabase.
- No es asesoramiento legal; prepara y publica una política de privacidad y condiciones adecuadas a tu actividad y jurisdicción.

## Paso 1 — Crear backend gratuito

1. Crea una cuenta en Supabase y un proyecto.
2. En el panel del proyecto, abre **SQL Editor**.
3. Copia y ejecuta el contenido de `schema.sql`.
4. En **Project Settings / API** copia Project URL y la clave publicable (o anon legacy).
5. Abre `config.js` y sustituye los dos valores `PEGA_AQUI...` y `tu-correo@example.com`.
6. En **Authentication / Users**, crea manualmente tu usuario administrador con tu correo y una contraseña fuerte. Desactiva el registro público de usuarios si está disponible. No compartas credenciales.
7. En **Authentication / URL Configuration**, añade la URL de tu web cuando la hayas publicado.

La clave del navegador debe ser únicamente la clave publicable/anon. **Nunca** pegues una `service_role` key en archivos web.

## Paso 2 — Publicar gratis con GitHub Pages

1. Crea una cuenta en GitHub y un repositorio nuevo, por ejemplo `chicas-casting`.
2. Sube todos los archivos de esta carpeta a la raíz del repositorio.
3. En el repositorio abre **Settings → Pages**.
4. En la sección de publicación elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`, y guarda.
5. GitHub mostrará una dirección parecida a `https://TU-USUARIO.github.io/chicas-casting/`.
6. Añade esa URL a la configuración de URL de Supabase Auth y prueba el acceso desde `.../admin.html`.

## Paso 3 — Prueba de seguridad antes de compartir

- Comprueba que el inicio de sesión de administrador funciona.
- Publica un anuncio de prueba, carga una imagen y verifica que aparece en la página pública.
- Confirma que borradores y anuncios cerrados no aparecen en la portada.
- Intenta abrir el panel en una ventana privada sin iniciar sesión: no debe mostrar los anuncios de administración.
- No habilites el registro público. Solo crea manualmente tu usuario administrador.
- Revisa las políticas de Supabase antes de subir datos reales.

## Límites de esta versión inicial

- Las imágenes subidas se guardan en un bucket público para que los visitantes puedan verlas; no subas imágenes sensibles o sin autorización.
- La función de eliminar anuncios no borra automáticamente los archivos de imagen antiguos del almacenamiento.
- El panel ofrece login por email y contraseña, pero debes configurar Supabase y comprobar las políticas antes de utilizarlo en producción.
- Un alojamiento gratuito puede tener límites o cambiar sus condiciones.
