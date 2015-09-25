# Alias

Para configurar un alias, se usa la siguiente sintaxis
```
git config --global alias.<al> "<com>"
```
Donde \<al\> es el alias que sustituira al comando \<com\>.

Un ejemplo de algunos alias utiles son
```
alias.st=status
alias.a=add
alias.aa=add --all
alias.co=commit -m
alias.story=log --oneline --decorate --graph --all
alias.ch=checkout
```
De esa forma, podemos utilizar un comando como
```
git co "Initial commit"
```
En vez del antiguo
```
git commit -m "Initial commit"
```
Lo cual es obviamente mucho más cómodo
