# Noshy

Monorepo que integra los repositorios de backend y frontend de Noshy como submódulos de git.

## Estructura

```
noshy/
├── backend/   → https://github.com/maybeimder/noshy-backend
└── frontend/  → https://github.com/maybeimder/noshy-frontend
```

## Clonar el monorepo

```bash
git clone --recurse-submodules https://github.com/maybeimder/noshy.git
```

Si ya lo clonaste sin submódulos:

```bash
git submodule update --init --recursive
```

## Actualizar submódulos a su último commit

```bash
git submodule update --remote --merge
```

## Trabajar dentro de un submódulo

Cada carpeta en `apps/` es un repositorio git independiente con su propio historial y remoto.

```bash
cd backend
git checkout -b mi-rama
# ... cambios ...
git push origin mi-rama
```

Luego, desde la raíz del monorepo, registra el nuevo commit del submódulo:

```bash
cd ..
git add backend
git commit -m "chore: bump backend submodule"
```
