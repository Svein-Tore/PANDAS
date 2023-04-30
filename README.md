# Pandas for IT-2
Vi har i dette faget jobbet med JavaScript.  Dette er et programmeringsspråk som fungerer bra for å innhente og presentere reelle datasett. Men når man skal analysere data så er ikke JavaScript et spesielt godt verktøy.  Da er det nyttig å bruke et verktøy som heter Pandas.  Dette verktøyet er laget for Python.  Vi skal derfor gjøre noe morsomt. Vi skal bruke noe som heter PyScript.  Dette er Python i nettleseren.  Hvordandette gjøres er besrkvet  i psdf dokumentet pandas.pdf som du finner under filer idette repositoriet.  I dette pedf dokumenteter det fler kdoesnutter. Siden diss ikke kan lastes ned er disse kodesnuttene lagt inn her og kan enkelt lastes ned.  Sidetallene henviser til sidetallet i pdf dokumentet.

## Hovedkode
Hovedkoden er et HTML dokument (se  s. 2).  Vi legger Python koden vår inn i taggen som heter <py-repl>. Når vi bruker <py-repl> taggen vil Pythnon koden vises på nettsiden i ewn REPL (Read Evaluate Print Loop, ala det vi har i Jupyter Notebook).  Dette kan vi endre ved på erstate <py-repl> taggen med en <py-script> tagg.
    
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
## kode s. 3:
```python    
    import pandas as pd
    import matplotlib.pyplot s plt
    from pyodide.http import open_url
    import json
    data=[{"navn":"Per","adresse":"skoleveien 5"},{"navn":"Ola","adresse":"skoleveien 6"}]
    df=DataFrame(data)
    display(df)
```    
