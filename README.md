# electron-git-merge

Aplicación que utliza git para visualizar los commits y logs de manera eficiente.

## 👀 Dependencias

- `electron`
- `react`

## 🛫 Creación del proyecto

```sh
npm create electron-vite

npm install

npm i vite-tsconfig-paths
```

```En el archivo vite.config.ts

  import tsConfigPaths from 'vite-tsconfig-paths'

  export default defineConfig(({ command }) => {
    rmSync('dist-electron', { recursive: true, force: true })

    const isServe = command === 'serve'
    const isBuild = command === 'build'
    const sourcemap = isServe || !!process.env.VSCODE_DEBUG

    return {
      plugins: [
        react(),
        tsConfigPaths(),
        electron([])
      ]
    }
  })
```

# Versiones

` Node v16.20.0`


## Uso

Todavía no averiguo

## 📂 Estructura de archivos 

```tree
├── electron                                 Electron-related code
│   ├── main                                 Main-process source code
│   └── preload                              Preload-scripts source code
│
├── release                                  Generated after production build, contains executables
│   └── {version}
│       ├── {os}-{os_arch}                   Contains unpacked application executable
│       └── {app_name}_{version}.{ext}       Installer for the application
│
├── public                                   Static assets
└── src                                      Renderer source code, your React application
```