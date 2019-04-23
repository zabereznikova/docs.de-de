---
title: Ableiten von Tabellen
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181830"
---
# <a name="inferring-tables"></a>Ableiten von Tabellen
Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen. Führen Sie die folgenden XML-Strukturen in einer Tabelle für die **DataSet** Schema:  
  
-   Elemente mit Attributen  
  
-   Elemente mit untergeordneten Elementen  
  
-   Sich wiederholende Elemente  
  
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
  
 Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden. Wenn das Dokumentelement verfügt über keine Attribute und keine untergeordneten Elemente, die als Spalten hergeleitet werden, wird das Element als abgeleitet eine **DataSet**. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
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
  
 Beim Herleiten ergibt eine **DataSet** mit dem Namen "DocumentElement", die eine Tabelle mit dem Namen "Element1".  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
