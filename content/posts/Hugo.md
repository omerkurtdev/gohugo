---
title: "Hugo ile Site Oluşturmak"
date: 2020-04-16T21:21:35+03:00
draft: false
tags: ["Hugo","Github","Gohugo"]
description: "Bu yazımda sizlere Hugo ile site kurmayı ve Github’da yayınlamayı anlatacağım"
---
Bu yazımda sizlere [Hugo][86df98c1] ile site kurmayı ve Github'da yayınlamayı anlatacağım.

# **Hugo Kurulumu**

Hugo'yu [kurmak](https://gohugo.io/getting-started/installing/) için bu dokümanı takip edebilirsiniz.

## **macOS**

```
brew install hugo
```
{{< youtube WvhCGlLcrF8>}}

## **Linux**

## **Snap İle Yüklemek**
```
snap install hugo --channel=extended
snap install hugo
```

## **Debian ve Ubuntu**
```
sudo apt-get install hugo
```

## **Fedora, Red Hat ve CentOS**
```
sudo dnf install hugo
```
# **Site Oluşturmak**
Bilgisayarımıza Hugo'yu kurduktan sonra aşağıdaki komutları kullanarak sitemizi oluşturabiliriz.
```
hugo new site hugo-site
cd hugo-site
```
Artık sitemiz oluştu ama içinde şu an tema yok. Hadi şimdi tema indirelim. Tema indirmek için şu [linke](https://themes.gohugo.io/) bakabilirsiniz. Temamızı seçtikten sonra şu komutları uygulayalım. Ben [blackburn](https://themes.gohugo.io/blackburn/) seçtim.

```
git submodule add https://github.com/yoshiharuyamashita/blackburn.git themes/blackburn

```
Temamızı indirdikten sonra içinde bulunan exampleSite dizinine gidip config.toml belgesini kopyalayıp bizim config.toml yapıştıralım. Config belgemizin içindeki parametreleri [düzenleyelim](https://gohugo.io/getting-started/quick-start/). Configin içini böyle düzeltelim.

```
baseURL = "https://<github_username>.github.io/"
languageCode = "en-us"
title = "Minimal"
theme = "minimal"
disqusShortname = "username" # delete this to disable disqus comments
googleAnalytics = ""
publishDir = "<github_username>.github.io"
```
Belgemizin içindeki publishDir HTML dosya yolunu gösterir.

Bu arada draft: true olduğu sürece  postlarımız sitemizde gözükmez. Dizinimizin içinde 'archetypes' dosyasına girip 'default.md' belgesindeki draftı false yapabilirsiniz.


# **Github'da Yayınlamak**

2 tane Github reposu oluşturmak zorundayız çünkü Github doğrudan Hugo gibi frameworkleri desteklemiyor. Bir reponun adı hugo_site olsun, diğer reponun adı username.github.io

Hadi sitemizin HTML kodlarını oluşturalım.

`Hugo`

Artık github_username.github.io adlı bir dosyamız oluştu.

```
git remote add origin git@github.com:<github_username>/hugo_site.git
git add .
git commit -m "initial commit"
git push -u origin master
```
Son olarak diğer repomuzuda Github sayfamıza eşitleyelim.

```
cd <github_username>.github.io
git remote -v
> origin git@github.com:<github_username>/<github_username>.github.io.git (fetch)
> origin git@github.com:<github_username>/<github_username>.github.io.git (push)

git add .
git commit -m "initial commit"
git push origin master
```

Şimdi github_username.github.io adlı repomuzun ayarlarına gidip sitemizi yayınlayalım. İşte bu kadar, eğer sorularınız bu gönderinin altına ya da diğer hesaplarımdan sorabilirsiniz.


  [86df98c1]: https://gohugo.io/ "Hugo"

