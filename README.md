# HTBmachines

![Bash](https://img.shields.io/badge/Shell-Bash-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Linux-yellow?style=flat-square)

Herramienta de terminal para **buscar y filtrar máquinas de HackTheBox** directamente desde la consola, sin abrir el navegador. Consulta nombre, sistema operativo, dificultad y enlaces de walkthrough en YouTube.

![demo](docs/demo.gif)

##  Características

-  Búsqueda de máquinas por nombre
-  Filtrado por sistema operativo (Linux / Windows)
- Filtrado por nivel de dificultad (Fácil, Media, Difícil, Insane)
-  Filtrado combinado (OS + dificultad)
- Búsqueda de link de YouTube asociado a una máquina
- Auto-actualización del set de datos local
-  Salida con colores y trazas claras

##  Requisitos

- `bash`
- `curl`
- [`js-beautify`](https://github.com/beautify-web/js-beautify) (`npm install -g js-beautify`)
- `sponge` (paquete `moreutils`)

Instalación de dependencias en Debian/Ubuntu:

```bash
sudo apt install moreutils npm -y
sudo npm install -g js-beautify
```

##  Instalación

```bash
git clone https://github.com/tu-usuario/htb-search-tool.git
cd htb-search-tool
chmod +x htb-search.sh
./htb-search.sh -u   # descarga la base de datos inicial
```

### Instalación global (opcional)

Para poder usar el comando `htb-search` desde cualquier carpeta:

```bash
./install.sh
```

##  Uso

```bash
./htb-search.sh [opciones]
```

| Flag | Descripción | Ejemplo |
|------|-------------|---------|
| `-m <nombre>` | Buscar una máquina por nombre | `-m Tentacle` |
| `-o <os>` | Filtrar por sistema operativo | `-o Linux` |
| `-d <dificultad>` | Filtrar por dificultad | `-d Difícil` |
| `-y <nombre>` | Obtener link de YouTube de una máquina | `-y Tentacle` |
| `-u` | Descargar/actualizar la base de datos local | `-u` |
| `-h` | Mostrar panel de ayuda | `-h` |

### Ejemplos

```bash
# Buscar información de una máquina puntual
./htb-search.sh -m Lame

# Ver todas las máquinas Windows
./htb-search.sh -o Windows

# Ver todas las máquinas de dificultad Insane
./htb-search.sh -d Insane

# Combinar OS + dificultad
./htb-search.sh -o Linux -d Media

# Obtener el walkthrough de YouTube de una máquina
./htb-search.sh -y Lame

# Actualizar la base de datos local
./htb-search.sh -u
```


## Licencia

Distribuido bajo la licencia MIT. Consulta [LICENSE](LICENSE) para más información.
