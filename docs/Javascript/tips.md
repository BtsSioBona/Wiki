### Useful Regex Patterns 
[Useful Regex Patterns ](https://projects.lukehaas.me/regexhub/ "CSSSPIN") : des Regex très simples d'utilisation.
- Exemple Regex d'une IPV4
```js
/^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/
```





###  Retire toutes les valeurs négatives d'un tableau :rocket::rocket::rocket::rocket:

```js
function filterMeh(arr) {
  return arr.filter(Boolean);
}
```


###  Déchiffre un Code César, avec le décalage donné :rocket::rocket::rocket::rocket:



```js
function caesarsCipher(str, decalage) {
  return str.toUpperCase().replace(/[A-Z]/g, (L) => String.fromCharCode(65 + (L.charCodeAt(0) - 65 + decalage) % 26));
}
}
```



