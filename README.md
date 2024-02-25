# Pandas for IT-2
Vi har i dette faget jobbet med JavaScript.  Dette er et programmeringsspråk som fungerer bra for å innhente og presentere reelle datasett. Men når man skal analysere data så er ikke JavaScript et spesielt godt verktøy.  Da er det nyttig å bruke et verktøy som heter Pandas.  Dette verktøyet er laget for Python.  Vi skal derfor gjøre noe morsomt. Vi skal bruke noe som heter PyScript.  Dette er Python i nettleseren.  Hvordandette gjøres er besrkvet  i psdf dokumentet pandas.pdf som du finner under filer idette repositoriet.  I dette pdf dokumenteter det flere kodesnutter. Siden disse ikke kan lastes ned er disse kodesnuttene lagt inn her og kan enkelt lastes ned.  Sidetallene henviser til sidetallet i pdf dokumentet.

### Hovedkode
Hovedkoden er et HTML dokument (se  s. 2).  Vi legger Python koden vår inn i taggen som heter <py-repl>. Når vi bruker <py-repl> taggen vil Pythnon koden vises på nettsiden i en REPL (Read Evaluate Print Loop, ala det vi har i Jupyter Notebook).  Dette kan vi endre ved på erstate <py-repl> taggen med en <py-script> tagg.
    
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
### kode s. 3:
```python    
    import pandas as pd
    import jinja2
    import matplotlib.pyplot as plt
    from pyodide.http import open_url
    import json
    data=[{"navn":"Per","adresse":"skoleveien 5"},{"navn":"Ola","adresse":"skoleveien 6"}]
    df=pd.DataFrame(data)
    display(df)
```    
### kode nr. 1 s. 6:
```python    
    import pandas as pd
    import jinja2
    import matplotlib.pyplot as plt
    from pyodide.http import open_url
    import json
    data=[{"navn":"Per","adresse":"skoleveien 5"},{"navn":"Ola","adresse":"skoleveien 6"}]
    df=DataFrame(data)
    display(df.loc[:,["navn"]])
```   
### kode nr. 2 s. 6:
```python    
    import pandas as pd
    import jinja2
    import matplotlib.pyplot as plt
    from pyodide.http import open_url
    import json
    data=[{"navn":"Per","adresse":"skoleveien 5"},{"navn":"Ola","adresse":"skoleveien 6"}]
    df=DataFrame(data)
    display(df.loc[[0],["navn"]])
```   
### kode nr. 3 s. 6:
```python    
    import pandas as pd
    import jinja2
    import matplotlib.pyplot as plt
    from pyodide.http import open_url
    import json
    data=[{"navn":"Per","adresse":"skoleveien 5"},{"navn":"Ola","adresse":"skoleveien 6"}]
    df=DataFrame(data)
    display(df.loc[[0,1],["navn"]])
```   
### kode nr. 1s. 7:
```python    
    import pandas as pd
    import jinja2
    import matplotlib.pyplot as plt
    from pyodide.http import open_url
    import json
    data=[{"navn":"Per","adresse":"skoleveien 5"},{"navn":"Ola","adresse":"skoleveien 6"}]
    df=DataFrame(data)
    display(df.loc[[1,0],["navn"]])
```
### kode s. 9:
```python
    import pandas as pd
    import jinja2
    import matplotlib.pyplot as plt
    from pyodide.http import open_url
    import json
    data=[
            {"navn":"Per","adresse":"skoleveien 5","alder":;45,"hoyde":176,"vekt":79},
            {"navn":"Ola","adresse":"skoleveien 6","alder":56,"hoyde":186,"vekt":89},
            {"navn":"Hans","adresse":"skoleveien 8","alder":66,"hoyde":197,"vekt":99}
    ]
    df=DataFrame(data)
    display(df)
```    
### kode s. 10:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   data=[
            {"navn":"Per","adresse":"skoleveien 5","alder":;45,"hoyde":176,"vekt":79},
            {"navn":"Ola","adresse":"skoleveien 6","alder":56,"hoyde":186,"vekt":89},
            {"navn":"Hans","adresse":"skoleveien 8","alder":66,"hoyde":197,"vekt":99}
    ]
    df=DataFrame(data)    
    farge=['r','g','#0000FF']
    linje=['g','b','r']
    fig,ax=plt.subplots(figsize=(8,3),layout='constrained')
    for i i range (0,len(df.index)):
        ax.bar(df.loc[i,"navn"],df.loc[i,"vekt"],color=farge[i],edgecolor=linje[i],df.loc[i,"vekt"],width=0.2)
    ax.legend(bbox_to_anchor=(1,1))
    ax.set_title("Vekt for ulike personer")
    display(plt)
```    
### kode s. 12:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   df=pd.read_json(open_url("navn.json"))
   farge=['r','g','#0000FF']
   linje=['g','b','r']
   fig,ax=plt.subplots(figsize=(8,3),layout='constrained')
   for i i range (0,len(df.index)):
       ax.bar(df.loc[i,"navn"],df.loc[i,"vekt"],color=farge[i],edgecolor=linje[i],df.loc[i,"vekt"],width=0.2)
   ax.legend(bbox_to_anchor=(1,1))
   ax.set_title("Vekt for ulike personer")
   display(plt)
```    
### kode nr. 1 s. 14:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   df=pd.read_json(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   display(df)
```    
### kode nr. 2 s. 14:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   df=pd.read_json(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   display(df['values'])
```
### kode s. 15:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize( data,record_path=["values"])
   display(df)
```
### kode s. 16:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize(data,record_path=["values"],meta=["station","zone"])
   df1=df[['fromTime','toTime','value','color','station']]
   display(df1)
```
### kode s. 19:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   def row_style(row):
       return pd.Series(
       'background-color:#'+row.color+';'+
       'color:blue;'+
       'font-size:20px;'
       ,row.index)
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize(data,record_path='values')
   df1=df[['fromTime','toTime','value','color']]
   display(df1.style.apply(row_style, axis=1))
```    
### kode s. 21
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   def row_style(row):
       return pd.Series(
       'background-color:#'+row.color+';'+
       'color:blue;'+
       'font-size:20px;'
       ,row.index)
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize(data,record_path='values')
   df1=df[['fromTime','toTime','value','color']]
display(df1.style.apply(row_style, axis=1).hide(axis="columns",subset='color').hide(axis="index").set_table_styles(
    [
        {'selector':'th,td','props':
         'border: 1px solid black;'    
        }
    ]
 ).set_table_attributes('style="border-collapse:collapse"'))   
```    
### kode s. 23:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize(data,record_path='values')
   avstand=-0.3
   fig,ax=plt.subplots(figsize=(11,6),layout='constrained') 
   for i in range (0,len(df.index)):
       ax.bar(df.loc[i,"fromTime"],df.loc[i,"value"],color="#"+df.loc[i,"color"],width=0.5)
   disply(plt) 
```    
### Kode s. 25:
```python
   import pandas as pd
   import jinja2 
   import matplotlib.pyplot as plt
   from pyodide.http import open_url
   import json
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize(data,record_path='values')
   avstand=-0.3
   fig,ax=plt.subplots(figsize=(11,6),layout='constrained') 
   for i in range (0,len(df.index)):
       ax.bar(df.loc[i,"fromTime"],df.loc[i,"value"],color="#"+df.loc[i,"color"],width=0.5)
       ax.text(avstand,df.loc[i,"value"]+1,df.loc[i,"value"])
       avstand=avstand+1
    plt.xticks(rotation=90)
    plt.title('luftkvalitetsindeks')
    plt.ylabel('luftkvalitetsindeks (mikrogram/m^3')
    plt.xlabel('dato')
   disply(plt) 
```        
### kode s. 27:
```python    
   import pandas as pd
   import jinja2 
   import matplotlib.pyploy as plt
   from pyodide.http import open_url
   import json
   data=json.load(open_url("https://api.nilu.no/aq/historical/2022-02-02/2022-02-03/ids/3124"))
   df=pd.json_normalize(data,record_path='values') 
   df2=df['index'].value_counts().div(len(df.index)).multiply(100)
   fig,ax=plt.subplots()
   ax.pie(df2,labels=['lav','moderat','høy'],autopct='%1.1f%%',colors=['#6ee86e','#ff9900','#ff0000']) 
   display(plt) 
```    
## kode s. 29
```python
import js
import jinja2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyodide.http import open_url
df=pd.read_json(open_url("./05.json"))
s=df.start_station_name.value_counts()
mest_pop=s.head(3)
minst_pop=s.tail(3)
s=pd.concat([mest_pop,minst_pop])
fig,ax=plt.subplots()
ax.bar(s.index,s,color=['r','g','b','y','c','m'])
plt.title('Tre mest og minst populære startlokasjoner')
plt.xlabel('startlokasjon')
plt.ylabel('Antall (popularitet)')
plt.xticks(rotation=30)
plt.tight_layout()
display(plt)
```
## Kode s. 30
```python
import js
import jinja2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyodide.http import open_url
df=pd.read_json(open_url("./05.json"))
df2=df.groupby('end_station_name').mean(numeric_only="True").sort_values('duration',ascending=False).head(3)
df2['min']=df2['duration'].div(60).round(0)
fig,ax=plt.subplots()
ax.bar(df2.index,df2['min'],color=['r','g','b'])
plt.xlabel('sluttlokasjon')
plt.ylabel('Minutter')
plt.title('Sluttlokasjonene med høyeste gjennmsnittsvarighet')
display(plt)    
```    
### kode s. 31
```python
import js
import jinja2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyodide.http import open_url
df=pd.read_json(open_url("./05.json"))
df['dato']=pd.to_datetime(df['started_at'])
df['ukedag_nr']=df['dato'].dt.weekday
s=df['ukedag_nr'].value_counts().sort_index()
dager=['mandag','tirsdag','onsdag','torsdag','fredag','lørdag','søndag']
fig,ax=plt.subplots()
ax.bar(dager,s,color=['r','b','g','c','m','y','k'])
plt.title('Antall turer totalt per dag')
plt.ylabel('Antall turer')
display(plt)
```    
### kode s. 32
```python
import js
import jinja2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyodide.http import open_url
df=pd.read_json(open_url("./05.json"))
s=df.start_station_name.value_counts()
mest_pop=s.head(3)
minst_pop=s.tail(3)
s=pd.concat([mest_pop,minst_pop])
fig,ax=plt.subplots()
ax.bar(s.index,s,color=['r','g','b','y','c','m'])
for bars in ax.containers:
    ax.bar_label(bars)
plt.title('Tre mest og minst populære startlokasjoner')
plt.xlabel('startlokasjon')
plt.ylabel('Antall (popularitet)')
plt.xticks(rotation=30)
plt.tight_layout()
display(plt)
```    
### kode s. 33
```python
import js
import jinja2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyodide.http import open_url
df=pd.read_json(open_url("./05.json"))
df2=df.groupby('end_station_name').mean().sort_values('duration',ascending=False).head(3)
df2['min']=df2['duration'].div(60).round(0)
fig,ax=plt.subplots()
ax.bar(df2.index,df2['min'],color=['r','g','b'])
for bars in ax.containers:
    ax.bar_label(bars)
plt.xlabel('Sluttlokasjon')
plt.ylabel('Minutter')
plt.title('Sluttlokasjoner med høyeste gjennomsnittsvarighet')
display(plt)
```    
### kode s. 34
```python
import js
import jinja2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyodide.http import open_url
df=pd.read_json(open_url("./05.json"))
df['dato']=pd.to_datetime(df['started_at'])
df['ukedag_nr']=df['dato'].dt.weekday
s=df['ukedag_nr'].value_counts().sort_index()
dager=['mandag','tirsdag','onsdag','torsdag','fredag','lørdag','søndag']
fig,ax=plt.subplots()
ax.bar(dager,s,color=['r','g','b','c','m','y','k'])
for bars in ax.containers:
    ax.bar_label(bars)
plt.title('Antall turer totalt per dag')
plt.ylabel('Antall turer')
display(plt)
```    
