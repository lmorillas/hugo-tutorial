---
title: "Menús"
date: 2021-01-05
weight: 19
description: 

---

{{% pageinfo %}}
Creación de menús a partir de parámetros en `config.yaml`

**Documentación:**  
* https://gohugo.io/content-management/menus/
* https://gohugo.io/templates/menu-templates/

{{% /pageinfo %}}

## Menús en `config.yaml`



https://gohugo.io/templates/menu-templates/#site-config-menus

```yaml
menu:
  main:
  - identifier: blog
    name: Sección de Blog
    title: sección blog 
    url: /blog/
    weight: -110

```
> Nota: el `identifier` tiene que coincidir con el nombre de una sección

## Menús en el frontmatter

También se pueden definir menús en el frontmatter de cada página

```yaml
---
title: Menu Templates
linktitle: Menu Templates

menu:
  docs:
    title: "how to use menus in templates"
    parent: "templates"
    weight: 130
---
```

## Ejemplo en las plantillas

```html
<ul>
{{ range .Site.Menus.main }}
  <li><a href="{{ .URL }}">{{ .Name }}</a></li>
{{ end }}
</ul>
```
Aquí tiene ejemplos más complejos (con submenús, etc): https://gohugo.io/templates/menu-templates/#example-templates


## Tarea

Adapta un menú de esta página para mostrarlo con Hugo https://getbootstrap.com/docs/5.2/examples/navbars Usa solo un nivel en el menú, sin **dropdown**

> Ejemplo: expand at sm

```html
 <nav class="navbar navbar-expand-sm navbar-dark bg-dark" aria-label="Third navbar example">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Expand at sm</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarsExample03" aria-controls="navbarsExample03" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarsExample03">
        <ul class="navbar-nav me-auto mb-2 mb-sm-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Acme</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="acercade">Acerca de</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="contacto">Contacto</a>
          </li>
          
        </ul>
        <form role="search">
          <input class="form-control" type="search" placeholder="Search" aria-label="Search">
        </form>
      </div>
    </div>
  </nav>
```