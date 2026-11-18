# Finanzas Personales — despliegue y verificaciones

Frontend: HTML/CSS/JS estático. Backend existente: Supabase `kzpjlemsssmukimvcqcp`. No se necesitan bases de datos adicionales.

- Producción: `public/index.html` (ruta `/`).
- Beta: `public/beta/index.html` (ruta `/beta/`) con guardados bloqueados por defecto; **no es aislamiento de datos**, comparte proyecto Supabase.
- Captura iPhone: `public/captura/index.html` y rutas `/?quick=expense` / `/?quick=income`.
- GitHub: `main` (fuente de publicación); `develop` para propuestas sin desplegarlas automáticamente.
- Render: tipo **Static Site**, comando `echo Publicando HTML estatico`, directorio de publicación `public`, rama `main`. No crear servicios de pago.
- El repositorio es privado, pero la web desplegada tendrá una URL pública. El acceso a datos requiere Supabase Auth y RLS.
- Supabase Auth requiere añadir la URL HTTPS real en **Site URL** y **Redirect URLs** antes de probar confirmación de email y restablecimiento de contraseña.
- No guardar contraseñas, tokens, CVV, NIP ni números completos de tarjeta en GitHub.
- El cifrado bancario y la contraseña maestra global siguen sujetos a auditoría; evitar incorporar datos bancarios reales hasta terminar pruebas.
- Se requieren pruebas con cuentas reales de prueba: confirmación de correo, CRUD, políticas RLS con dos usuarios, Safari iOS y cifrado/desbloqueo.
