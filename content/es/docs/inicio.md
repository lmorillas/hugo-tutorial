---
title: "Inicio"
date: 2022-09-16
weight: 15

  
---

{{% pageinfo %}}
**Objetivo:** Instalación requisitos

**Contenidos:** 
* hugo
* git
* editor de texto

> Vamos a seguir este tutorial: https://gohugo.io/getting-started/quick-start/

{{% /pageinfo %}}


## Instalación Hugo

https://gohugo.io/installation/


### Previo

* Instalar **git** https://git-scm.com/downloads o https://gitforwindows.org/
* Instalar **go**  https://go.dev/doc/install
> * Chocolatey (Windows) https://chocolatey.org/install#individual ?
> * https://sass-lang.com/install/

### Instalar **hugo**

{{% pageinfo %}}
Recuerda:
* Instalar 
* Configurar el **path** del sistema
{{% /pageinfo %}}

### comprobamos

```bash
$ hugo version
```

## Instalación de un editor de texto

Instala Visusal Studio Code https://code.visualstudio.com/

## Configurar Git
* [Crear cuenta en Github](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account) (si no la tienes)
* https://docs.github.com/en/get-started/quickstart/set-up-git

### username  y email
* [username](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git)
* [email](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address)

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email zzz@xxx.com
```

### Autenticación
* Tokens https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

* https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md

> TAREA: Revisa cómo hacerlo desde [VSCode](https://code.visualstudio.com/docs/sourcecontrol/github)
