---
title: Ableiten von Elementtext
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 6ffe8f2fbf01fbe8dfa9d78f3dfb9e39b6e80b16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879631"
---
# <a name="inferring-element-text"></a>Ableiten von Elementtext
Wenn ein Element Text enthält und keine untergeordneten Elemente hat, die per Rückschluss abgeleitet werden, wie z. B. (Elemente mit Attributen) oder sich wiederholende Elemente eine neue Spalte mit dem Namen Tabellen **TableName_Text** wird die Tabelle, die für das Element hergeleitet wird hinzugefügt. Der in dem Element enthaltene Text wird einer Tabellenzeile hinzugefügt und in der neuen Spalte gespeichert. Die **ColumnMapping** -Eigenschaft der neuen Spalte auf festgelegt **MappingType.SimpleContent**.  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten: **attr1** und **Element1_Text**. Die **ColumnMapping** Eigenschaft der **attr1** Spalte festgelegt **MappingType.Attribute**. Die **ColumnMapping** Eigenschaft der **Element1_Text** Spalte festgelegt **MappingType.SimpleContent**.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Bei einem Element mit Text und untergeordneten Elementen, die ebenfalls Text enthalten, wird der Tabelle keine Spalte zum Speichern des Elementtexts hinzugefügt. Der in dem Element enthaltene Text wird ignoriert, während der Text in den untergeordneten Elementen in eine Tabellenzeile eingefügt wird. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 Die Herleitung wird einer Tabelle namens **Element1** mit einer Spalte, die mit dem Namen **ChildElement1**. Der Text für die **ChildElement1** Element wird in einer Zeile in der Tabelle enthalten sein. Der restliche Text wird ignoriert. Die **ColumnMapping** Eigenschaft der **ChildElement1** Spalte festgelegt **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
