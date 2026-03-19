# Organizador de Cundinas

Proyecto para la materia Frontend II enfocado en la organización de cundinas: participantes, aportaciones y control básico de pagos.

## Objetivo

Construir una aplicación frontend con buenas prácticas de desarrollo:

- Formato automático de código.
- Linting obligatorio.
- Pruebas unitarias.
- Flujo de trabajo con ramas, Pull Request y validación en CI.

## Stack del proyecto

- Vite
- JavaScript
- ESLint
- Prettier
- Vitest
- Husky + lint-staged

## Instalación

1. Clona el repositorio.
2. Instala dependencias:

```bash
npm install
```

3. Activa hooks locales:

```bash
git config core.hooksPath .husky
npm run prepare
```

## Scripts disponibles

```bash
npm run dev
npm run build
npm run lint
npm run lint:fix
npm run format
npm run format:check
npm run test
npm run test:watch
```

Nota para Windows PowerShell con políticas restringidas:

```bash
npm.cmd run test
npm.cmd run lint
```

## Estructura base

```text
src/
  calculadora.js
tests/
  calculadora.test.js
```

Esta estructura irá creciendo con los módulos de cundinas.

## Flujo de trabajo obligatorio

1. Crear rama de trabajo:

```bash
git checkout -b feature/nombre-de-tu-tarea
```

2. Desarrollar funcionalidad y sus pruebas.
3. Verificar localmente antes de commit:

```bash
npm run format
npm run lint
npm run test
```

4. Hacer commit:

```bash
git add .
git commit -m "feat: descripcion corta"
```

5. Subir la rama:

```bash
git push origin feature/nombre-de-tu-tarea
```

6. Abrir Pull Request hacia main.

## Reglas para main

En GitHub, proteger la rama main con:

- Require a pull request before merging.
- Require status checks to pass before merging (check de evaluacion).
- Require branches to be up to date before merging.
- Do not allow bypassing the above settings.

## Solución de problemas

1. Commit rechazado por Husky/lint-staged:

- Ejecuta format y lint:fix.
- Reagrega archivos y vuelve a intentar el commit.

2. Falla CI aunque local pase:

- Ejecuta test completo antes de subir cambios.

3. Error de dependencias en CI:

- Verifica que package.json y package-lock.json estén actualizados y versionados.
