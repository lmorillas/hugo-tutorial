---
title: "Crear un tema"
date: 2017-01-05
weight: 18
description: 

---

{{% pageinfo %}}
Creación de un nuevo tema

**Documentación:**  
* https://gohugo.io/commands/hugo_new_theme
* https://gohugo.io/templates/
* https://gohugo.io/hugo-modules/theme-components/
{{% /pageinfo %}}

## Creación de un nuevo tema

```bash
$ hugo new theme <THEME_NAME>
$ hugo new theme basico

themes/basico/
├── LICENSE
├── archetypes
│ └── default.md
├── layouts
│ ├── 404.html
│ ├── _default
│ │ ├── baseof.html
│ │ ├── list.html
│ │ └── single.html
│ ├── index.html
│ └── partials
│
├── footer.html
│
├── head.html
│
└── header.html
├── static
│ ├── css
│ └── js
└── theme.toml
```


## Content blocks y partials

### themes/basico/layouts/_default/baseof.html

```go-html-template
<!DOCTYPE html>
<html>
  {{- partial "head.html" . -}}
  <body>
  {{- partial "header.html" . -}}
    <div id=​ "content"​ >
    {{- block "main" . }}{{- end }}
    </div>
  {{- partial "footer.html" . -}}
  </body>
</html>

```

### themes/basico/layouts/partials/head.html

```go-html-template
<head>
<meta charset=​ "utf-8"​ >
<meta name=​ "viewport"​ content=​ "width=device-width, initial-scale=1"​ >
<title>{{ .Site.Title }}</title>
</head>
```

### themes/basico/layouts/partials/header.html

```go-html-template
<header>
<h1>{{ .Site.Title }}</h1>
</header>
<nav>
<a href=​ "/"​ >Acme</a>
<a href=​ "/viajes"​ >Viajes</a>
<a href=​ "/contacto"​ >Contacto</a>
<a href=​ "/acercade"​ >Acerca de</a>
</nav>
```

### themes/basico/layouts/partials/footer.html

```go-html-template
<footer>
  <small>Copyright {{now.Format "2022"}} Yo.</small>
</footer>
```

### themes/basico/layouts/index.html

**Para Home Page** con el contenido que encuentre en `content/_index.md`

```go-html-template
{{ define "main" }}
{{ .Content }}
{{ end }}
```

### themes/basico/layouts/_default/single.html

**Páginas individuales**

```go-html-template
{{ define "main" }}
<h2>{{ .Title }}</h2>
{{ .Content }}
{{ end }}
```

### Algo de estilo

```basic_theme/portfolio/themes/basico/static/css/style.css```

```css

.container {
margin: 0 auto;
width: 80%;
}


nav, footer {
background-color: #333;
color: #fff;
text-align: center;
}

nav {
display: flex;
flex-direction: column;
}
nav > a {
flex: 1;
text-align: center;
text-decoration: none;color: #fff;
}

@media​ only screen and (min-width: 768px) {
nav { flex-direction: row; }
}

```

Modificamos el partial `head.html` para incluir el css

```go-html-template
<head>
<meta charset=​ "utf-8"​ >
<meta name=​ "viewport"​ content=​ "width=device-width, initial-scale=1"​ >
<title>{{ .Site.Title }}</title>

<link rel=​ "stylesheet"​ href=​ "{{ "​ css​ / ​ style​ . ​ css​ " ​ ​ | ​ relURL ​ }}"​ >
...
``` 

### themes/basico/layouts/_default/list.html

**Para listas de páginas**

```go-html-template
{{ define "main" }}
<h2>{{ .Title }}</h2>
<ul>
{{ range .Pages }}
<li><a href=​ "{{ .RelPermalink }}"​ >{{ .Title }}</a></li>
{{ end }}
</ul>
{{ end }}
```

```{{ range .Pages }}``` itera sobre las páginas que se encuentran en el directorio actual (sección).

## Tareas

* Crear un repositorio con esta tema en github
  * Luego podremos añadir el tema con  ```git submodule add https://github.com/<url_del_tema>.git themes/basico```
  
* Mueve la navegación a un nuevo **partial**
* Modifica el tema para que use boostrap. Más fácil usando el CDN de bootstrap.
* Crea un tema especial para los viajes. Tendrá que incluir un mapa con  [Leaflet](https://leafletjs.com/) https://leafletjs.com/examples/quick-start/
  * El mapa irá en el html de la página (no en el .md)
  * Tendremos que introducir las coordenadas de los viajes en el .md (frontmatter)