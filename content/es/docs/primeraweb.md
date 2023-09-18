---
title: "Mi primera web con Hugo"
date: 2022-09-16
weight: 20

  
---

{{% pageinfo %}}
**Objetivo:** Construcción de una primera web

Seguimos las instrucciones de https://gohugo.io/getting-started/quick-start/

{{% /pageinfo %}}

## Creación del sitio

> Archivo `.gitignore`
```
*back
public
```

### Instalación del tema como un módulo
En el ejemplo se instala como un `submódulo` de `git`

Pero también se puede instalar como un `módulo de hugo`

> https://gohugo.io/hugo-modules/use-modules/

> Aquí tienes un ejemplo: https://catherinepope.com/posts/add-hugo-theme-as-submodule/

* Inicializar módulo
```bash
hugo mod init <miweb>
 o 

hugo mod init github.com/<miusuario>/<mi repositorio>
```

* Actualizar los módulos
```bash
hugo mod get -u
```


* Usar un módulo para un tema

```toml
[module]
[[module.imports]]
    path = 'github.com/theNewDynamic/gohugo-theme-ananke'

```

```bash

```

## Añadir contenido

## Configurar el sitio

## Publicar nuestra web

### Github Pages
* https://gohugo.io/hosting-and-deployment/hosting-on-github/

### Netlify
* https://gohugo.io/hosting-and-deployment/hosting-on-netlify/

### Con un servidor web (AWS EC2)
* Crear una instancia EC2
* Instalar nginx
* Subir el contenido a la instancia
* (Configurar nginx)

### Despliegue en AWS S3 (+ CloudFront)
* Crear un bucket S3
* Subir el contenido a S3
* Configurar CloudFront
* Configurar Route53

