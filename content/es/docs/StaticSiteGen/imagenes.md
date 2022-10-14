---
title: "Imágenes"
date: 2021-01-05
weight: 20
description: 

---

{{% pageinfo %}}
Introducción a la manipulación de imágenes

**Documentación:**  
* https://gohugo.io/content-management/image-processing
* https://gohugo.io/content-management/page-bundles

{{% /pageinfo %}}

## Imágenes

Podemos incluir las imágenes locales en la carpeta `static` o creando `bundles` con nuestras páginas.

## Organización de las páginas en *manojos* (bundles)

```bash
$ hugo new viajes/galicia/index.md

```
Esto nos permite crear un directorio en esa nueva carpeta (`galicia`) y podemos pegar en un directorio `images` nuestras imágenes.


Podemos incluir las imágenes directamente en el markdown o usar el shorcode `{ { < figure src="..." >}}`:

```md
{ { < figure src="images/galicia.jpg" title="Galicia" >}}
```

También podemos crear un shortcode más preciso. Por ejemplo, este shortcode **dimensionaFigura.html**

```html
{{ $imagen := $.Page.Resources.GetMatch (.Get 0)}}
{{ $imagenReducida := $imagen.Resize "480x" }}

<figure class="figure">
  <a href="{{ $imagen.RelPermalink }}">
    {{ with $imagenReducida }}
    <img src="{{ .RelPermalink }}"
         width="{{ .Width }}" height="{{ .Height }}"
         alt="{{ $.Get 1 }}" class="figure-img img-fluid">
    {{ end }}
  </a>
  <figcaption class="figure-caption">{{ .Get 1 }}</figcaption>
</figure>
```

Que luego podemos usar así:

```html
{ { < dimensionaFigura "galicia.jpg" "Galicia" > }}
```