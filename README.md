# Pandas for IT-2
Vi har i dette faget jobbet med JavaScript.  Dette er et programmeringsspråk som fungerer bra for å innhente og presentere reelle datasett. Men når man skal analysere data så er ikke JavaScript et spesielt godt verktøy.  Da er det nyttig å bruke et verktøy som heter Pandas.  Dette verktøyet er laget for Python.  Vi skal derfor gjøre noe morsomt. Vi skal bruke noe som heter PyScript.  Dette er Python i nettleseren.  Hvordandette gjøres er besrkvet  i psdf dokumentet pandas.pdf som du finner under filer idette repositoriet.  I dette pedf dokumenteter det fler kdoesnutter. Siden diss ikke kan lastes ned er disse kodesnuttene lagt inn her og kan enkelt lastes ned.  Sidetallene henviser til sidetallet i pdf dokumentet.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Pyscript</title>
    <!-- Her leser vi inn pyscript biblioteket -->
    <script defer src="https://pyscript.net/latest/pyscript.js"></script>
</head>
<style>

</style>
<body>
<!-- I <py-config> taggen installerer vi pandas og andre aktuelle bibliotek -->
<py-config>
    packages = ["pandas","matplotlib","jinja2","requests"]
</py-config>
<!--
Inne i <py-repl> taggen kan vi skrive vanlig Python kode.
Når vi bruker repl så får vi vist Pyrthon koden i nettleseren
<py-repl> kan erstatters med <py-script>. Da vises ikke python koden.
-->
<py-repl>
```
```python
    print("Hello World")
```
```html
</py-repl>
</body>
</html>
```
