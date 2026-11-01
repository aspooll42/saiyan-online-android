# Saiyan Online para Android

Versión para Android del MMORPG 2D **Saiyan Online**, hecha con permiso del equipo de Saiyan Online.
Usa la misma cuenta y los mismos servidores que la versión de ordenador.

## Descargar

En [Releases](../../releases) está la última APK. Al abrirla por primera vez descarga los
recursos del juego (unos 520 MB), así que conviene estar en wifi.

Para instalarla hay que permitir "instalar aplicaciones desconocidas" para el navegador o el
gestor de archivos con el que la abras.

## Qué tiene la versión Android

- Pantalla completa a la resolución real del móvil, con la interfaz escalada para que se lea.
- Joystick y botones táctiles (atacar, bloquear, esquivar, ki, dash, coger, objetivo) que pulsan
  las teclas que el jugador tenga asignadas.
- Toque = clic, mantener pulsado = clic derecho, arrastrar = arrastrar.
- Un toque en la barra de técnicas las usa.
- Teclado de Android en los campos de texto (inicio de sesión, chat).
- Botón Atrás = Escape.
- Descarga de los recursos en el primer arranque.

## Cómo está hecho

El cliente de ordenador es [Intersect Engine](https://github.com/AscensionGameDev/Intersect-Engine)
0.8 con muchas modificaciones, sobre MonoGame y .NET 8. Este repositorio no incluye el código del
juego: contiene las herramientas que lo descompilan, lo corrigen y lo adaptan a Android.

1. `extraer_bundle.py` saca las DLL del ejecutable de .NET (single-file bundle).
2. `descompilar.sh` las descompila con ILSpy a proyectos C#.
3. `arreglar_csproj.py` y `arreglar_codigo.py` corrigen lo que ILSpy no reconstruye bien hasta que compila.
4. `adaptar_android.py` añade los cambios para Android (todos dentro de `#if ANDROID` o compatibles
   con el escritorio).
5. `android/SaiyanAndroid` es el proyecto MonoGame Android que compila todo eso. El código propio de
   Android está en `android/SaiyanAndroid/Plataforma/`:
   - `MainActivity.cs`: arranque, pantalla completa, botón Atrás.
   - `DescargaRecursos.cs`: descarga de los recursos la primera vez.
   - `ControlesTactiles.cs`: joystick y botones.
   - `TactilAndroid.cs`: el tacto como ratón.
   - `TecladoAndroid.cs`: teclado en pantalla.

Necesita el .NET SDK 8, la carga de trabajo `android`, el Android SDK (plataforma 34) y Java 17.

```bash
python3 extraer_bundle.py "/Applications/Saiyan Online.app/Contents/MacOS/jeu-apple" extraido
./descompilar.sh descompilado
python3 arreglar_codigo.py descompilado
python3 adaptar_android.py descompilado
./compilar.sh descompilado
cd android/SaiyanAndroid && dotnet build -c Release
```

`instalar_movil.sh` instala la APK en un móvil conectado por USB y le copia los recursos.

## Tienda

`tienda/` tiene el icono, el gráfico destacado, capturas, la ficha para Google Play y un borrador de
política de privacidad.

## Créditos

Saiyan Online es del equipo de Saiyan Online. Intersect Engine es software libre (GPLv3) de
Ascension Game Dev.
