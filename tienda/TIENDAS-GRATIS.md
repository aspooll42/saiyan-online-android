# Publicar Saiyan Online en tiendas gratuitas

Tiendas conocidas en las que darse de alta como desarrollador no cuesta dinero. En todas hay que
crear la cuenta uno mismo (datos personales, a veces documento de identidad) y aceptar su contrato.

## Lo que piden todas

| Campo | Valor |
|---|---|
| APK | `SaiyanOnline-0.1.0.apk` de la [release v0.1.0](https://github.com/aspooll42/saiyan-online-android/releases/tag/v0.1.0) |
| Nombre | Saiyan Online |
| Paquete | `com.saiyanonline.android` |
| Versión | 0.1.0 (código 1) |
| Categoría | Juegos → Rol |
| Precio | Gratis, sin compras dentro de la app, sin anuncios |
| Icono 512×512 | [`icono-512.png`](icono-512.png) |
| Gráfico 1024×500 | [`grafico-destacado-1024x500.png`](grafico-destacado-1024x500.png) |
| Capturas (horizontales) | [`captura-1.png`](captura-1.png) … [`captura-8.png`](captura-8.png) |
| Política de privacidad | https://github.com/aspooll42/saiyan-online-android/blob/main/tienda/privacidad.md |
| Descripción breve y completa | En [`FICHA-PLAY-STORE.md`](FICHA-PLAY-STORE.md) |
| Clasificación por edad | Violencia de fantasía; chat entre jugadores (normalmente PEGI 12 / 12+) |
| Requisitos | Android 7.0 o superior, internet; ~520 MB de descarga en el primer arranque |

Antes de enviar: rellena el correo de contacto en `privacidad.md` (lo piden todas) y revisa con el
equipo de Saiyan Online los datos que guarda el servidor.

## Samsung Galaxy Store

- Alta: https://seller.samsungapps.com — gratis, se puede como particular.
- Pasos: Add New Application → Android → idioma español → sube la APK en "Binary" →
  rellena "App Information" (textos, icono, capturas, categoría) → "Country/Region" (elige países) →
  "Content rating" → Submit.
- Revisión: unos días. Samsung prueba la app en varios Galaxy; aceptan juegos que descargan
  recursos al abrirse si se avisa en la descripción (ya lo hace).

## Uptodown

- Alta: https://developers.uptodown.com — gratis.
- Sube la APK y la ficha; es de las más visitadas en España y Latinoamérica.

## itch.io

- Alta: https://itch.io/register → "Upload new project". Gratis y lo más rápido (se publica al momento).
- Kind of project: Downloadable. Pricing: No payments. Sube la APK y marca "Android".
- Portada 630×500: recorta `grafico-destacado-1024x500.png`.

## Huawei AppGallery

- Alta: https://developer.huawei.com/consumer/en/appgallery — gratis, pide verificar identidad
  (documento y a veces tarjeta, sin cobro).
- App → Add → Android → sube la APK y la ficha → Submit. Revisión: unos días.

## APKPure

- Envío de apps: https://developer.apkpure.com (cuenta gratuita). Sube la APK y la ficha.

## Tiendas que no sirven

- **F-Droid**: solo admite software libre sin recursos privativos.
- **Amazon Appstore**: dejó de funcionar en móviles Android en 2025.

## Actualizaciones

Cada versión nueva: sube `ApplicationVersion` en `android/SaiyanAndroid/SaiyanAndroid.csproj`,
compila en Release (se firma solo con la clave de `publicar/firma/`) y sube la APK nueva a cada tienda
y a una release nueva de GitHub. Si la firma cambia, las tiendas rechazan la actualización.

## Aviso

Las tiendas retiran apps que usan nombres o personajes de franquicias sin licencia de sus dueños.
El permiso del equipo de Saiyan Online cubre su juego, no la marca Dragon Ball.
