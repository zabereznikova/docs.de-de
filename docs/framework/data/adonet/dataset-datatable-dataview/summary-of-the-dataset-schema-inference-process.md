---
title: Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 272e5762b7afd9f3ab24cbdec5f31bb120364815
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116063"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
Während des Rückschlussprozesses wird zunächst anhand des XML-Dokuments bestimmt, welche Elemente als Tabellen hergeleitet werden. Anschließend werden aus der übrigen XML die Spalten für diese Tabellen ermittelt. Bei geschachtelten Tabellen werden beim Rückschlussprozess geschachtelte <xref:System.Data.DataRelation>-Objekte und geschachtelte <xref:System.Data.ForeignKeyConstraint>-Objekte erstellt.  
  
 Im Folgenden finden Sie eine kurze Zusammenfassung der Rückschlussregeln:  
  
-   Elemente mit Attributen werden als Tabellen hergeleitet.  
  
-   Elemente mit untergeordneten Elementen werden als Tabellen hergeleitet.  
  
-   Sich wiederholende Elemente werden als einzelne Tabelle hergeleitet.  
  
-   Ein Dokument- oder Stammelement, das keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet würden, wird als <xref:System.Data.DataSet> hergeleitet. Andernfalls wird das Dokumentelement als Tabelle hergeleitet.  
  
-   Attribute werden als Spalten hergeleitet.  
  
-   Elemente, die keine Attribute oder untergeordnete Elemente aufweisen und sich nicht wiederholen, werden als Spalten hergeleitet.  
  
-   Für Elemente, die als geschachtelte Tabellen innerhalb von anderen Elementen abgeleitet werden, die ebenfalls abgeleitet werden als Tabellen, eine geschachtelte **DataRelation** wird zwischen den beiden Tabellen erstellt. Eine neue, primäre Schlüsselspalte, die mit dem Namen **TableName_Id** wird für beide Tabellen hinzugefügt, und verwendet die **DataRelation**. Ein **ForeignKeyConstraint** erstellt wird, zwischen den beiden Tabellen mithilfe der **TableName_Id** Spalte.  
  
-   Für Elemente, die als Tabellen hergeleitet werden und, die Text enthalten, aber keine untergeordneten Elemente haben, eine neue Spalte mit dem Namen **TableName_Text** für den Text der einzelnen Elemente der erstellt wird. Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.  
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Verwenden von XML in einem "DataSet"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- ["DataSets", "DataTables" und "DataViews"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
