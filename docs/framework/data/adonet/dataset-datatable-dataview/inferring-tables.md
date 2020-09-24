---
title: Ableiten von Tabellen
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 4a3d7b239dbc405cf2acae967b5be401dc772e38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177552"
---
# <a name="inferring-tables"></a>Ableiten von Tabellen

Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen. Die folgenden XML-Strukturen führen zu einer Tabelle für das **DataSet** -Schema:  
  
- Elemente mit Attributen  
  
- Elemente mit untergeordneten Elementen  
  
- Sich wiederholende Elemente  
  
## <a name="elements-with-attributes"></a>Elemente mit Attributen  

 Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## <a name="elements-with-child-elements"></a>Elemente mit untergeordneten Elementen  

 Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden. Wenn das Document-Element keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten abgeleitet werden, wird das Element als **DataSet**abgeleitet. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".  
  
 **DataSet:** NewDataSet  
  
 **Tabelle:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 Betrachten Sie alternativ dazu den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Der Rückschluss Prozess erzeugt ein **DataSet** mit dem Namen "DocumentElement", das eine Tabelle mit dem Namen "Element1" enthält.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="repeating-elements"></a>Sich wiederholende Elemente  

 Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>Weitere Informationen

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
