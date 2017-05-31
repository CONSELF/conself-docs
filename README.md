## Useful guides and links

* https://matcornic.github.io/hugo-learn-doc/cont/markdown/
* https://github.com/matcornic/hugo-learn-doc
* https://github.com/matcornic/hugo-theme-learn
* https://gohugo.io/tutorials/github-pages-blog/
* https://gohugo.io/content/markdown-extras/
* https://gohugo.io/extras/shortcodes/

## Hugo installation

Thanks to the simplicity of Hugo, this page is as empty as this theme needs requirements.

Just download [Hugo](https://github.com/spf13/hugo/releases) binary for your OS (Windows, Linux, Mac) : it’s that simple.

Check that your Hugo version installed is ```0.21``` with ```hugo version```.

## Hugo commands

Chapter page (_index.md files are considered as chapters): 

```
hugo new --kind chapter basics/_index.md
```

Content page:

```
hugo new basics/first-content.md
```

Site generation:

```
hugo
```

Site run:

```
hugo server
```

## Repository commit and site deployment

Command:

```
./deploy.sh "Your optional commit message"
```

or

```
./deploy.sh
```