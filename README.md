# Planimetro — Despliegue en Netlify

## Estructura
```
planimetro-netlify/
├── index.html                        ← app principal
├── netlify.toml                      ← configuración Netlify
├── netlify/functions/
│   └── anthropic-proxy.js            ← proxy serverless para la API
└── README.md
```

## Pasos para desplegar

### 1. Subir a GitHub
```bash
cd planimetro-netlify
git init
git add .
git commit -m "init planimetro"
gh repo create planimetro --public --push --source=.
```

### 2. Conectar en Netlify
- netlify.com → "Add new site" → "Import an existing project"
- Selecciona el repo `planimetro`
- Build command: (vacío)
- Publish directory: `.`

### 3. Añadir la API key
En Netlify → Site → Environment variables:
```
ANTHROPIC_API_KEY = sk-ant-...tu clave...
```

### 4. Redesplegar
Netlify → Deploys → "Trigger deploy" → Deploy site

La app estará en `https://tu-sitio.netlify.app`
