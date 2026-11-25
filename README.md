# Cuaderno Digital de Ocurrencias

Proyecto de titulación técnica del Instituto Khipu para el Área de Distribución de Agua Potable de SedaCusco. Esta base incluye la página inicial en español y la preparación para una futura conexión con Supabase y PostgreSQL.

## Instalación y ejecución local

1. Abre la carpeta raíz del repositorio en Visual Studio Code y abre una terminal PowerShell.
2. Comprueba que tienes Node.js y npm. Esta base se verificó con Node.js 26.13.1 y npm 11.20.0.
3. Instala las dependencias con las versiones registradas en `package-lock.json` y arranca el servidor.

   ```powershell
   node --version
   npm.cmd --version
   npm.cmd ci
   npm.cmd run dev
   ```

4. Abre `http://localhost:3000` en el navegador. Deben aparecer el título **Cuaderno Digital de Ocurrencias** y el subtítulo **Área de Distribución de Agua Potable — SedaCusco**. Si Next.js indica otro puerto en la terminal, usa la dirección que muestra.
5. Presiona `Ctrl+C` en la terminal para detener el servidor.

`npm.cmd` ejecuta npm en Windows aunque PowerShell tenga deshabilitados los scripts `.ps1`.

## Verificaciones

Con el servidor de desarrollo detenido, ejecuta estos comandos desde la raíz.

```powershell
npm.cmd run lint
npm.cmd run typecheck
npm.cmd run build
```

El primer comando revisa el código con ESLint. El segundo comprueba los tipos de TypeScript. El tercero genera la compilación de producción. Para probar esa compilación localmente, ejecuta `npm.cmd start` y abre `http://localhost:3000`.

## Variables de entorno

La página inicial funciona sin configurar Supabase. Cuando se integre Supabase, copia `.env.example` a `.env.local` y completa `NEXT_PUBLIC_SUPABASE_URL` y `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY` con los datos del proyecto. Las variables que empiezan con `NEXT_PUBLIC_` pueden ser visibles en el navegador. Usa la clave publicable y guarda las claves privadas fuera de esas variables. Git ignora `.env.local`.

## Carpetas principales

- `app/` contiene la página inicial, la estructura compartida y los estilos.
- `docs/` queda disponible para la documentación del proyecto.
- `supabase/migrations/` queda disponible para futuros cambios al esquema de PostgreSQL.
