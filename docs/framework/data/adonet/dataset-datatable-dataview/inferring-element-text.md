---
title: Ableiten von Elementtext
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 7389e24f39902edf041c3cd3502303b17fd008ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164687"
---
# <a name="inferring-element-text"></a>Ableiten von Elementtext

Wenn ein Element Text enthält und es keine untergeordneten Elemente gibt, die als Tabellen abgeleitet werden sollen (z. b. Elemente mit Attributen oder wiederholten Elementen), wird eine neue Spalte mit dem Namen **TableName_Text** der Tabelle hinzugefügt, die für das Element abgeleitet wird. Der in dem Element enthaltene Text wird einer Tabellenzeile hinzugefügt und in der neuen Spalte gespeichert. Die **ColumnMapping** -Eigenschaft der neuen Spalte wird auf **MappingType. SimpleContent**festgelegt.  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen **Element1** mit zwei Spalten: **attr1** und **Element1_Text**. Die **ColumnMapping** -Eigenschaft der **attr1** -Spalte wird auf **MappingType. Attribute**festgelegt. Die **ColumnMapping** -Eigenschaft der **Element1_Text** -Spalte wird auf **MappingType. SimpleContent**festgelegt.  
  
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
  
 Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen " **Element1** " mit einer Spalte mit dem Namen " **ChildElement1**". Der Text für das **ChildElement1** -Element wird in eine Zeile in der Tabelle eingeschlossen. Der restliche Text wird ignoriert. Die **ColumnMapping** -Eigenschaft der **ChildElement1** -Spalte wird auf **MappingType. Element**festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Weitere Informationen

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
