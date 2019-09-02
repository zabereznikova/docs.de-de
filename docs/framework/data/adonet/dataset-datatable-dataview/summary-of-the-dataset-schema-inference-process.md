---
title: Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 5266d08212e5259bd5b242a70d61e29ad9008006
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203247"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
Während des Rückschlussprozesses wird zunächst anhand des XML-Dokuments bestimmt, welche Elemente als Tabellen hergeleitet werden. Anschließend werden aus der übrigen XML die Spalten für diese Tabellen ermittelt. Bei geschachtelten Tabellen werden beim Rückschlussprozess geschachtelte <xref:System.Data.DataRelation>-Objekte und geschachtelte <xref:System.Data.ForeignKeyConstraint>-Objekte erstellt.  
  
 Im Folgenden finden Sie eine kurze Zusammenfassung der Rückschlussregeln:  
  
- Elemente mit Attributen werden als Tabellen hergeleitet.  
  
- Elemente mit untergeordneten Elementen werden als Tabellen hergeleitet.  
  
- Sich wiederholende Elemente werden als einzelne Tabelle hergeleitet.  
  
- Ein Dokument- oder Stammelement, das keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet würden, wird als <xref:System.Data.DataSet> hergeleitet. Andernfalls wird das Dokumentelement als Tabelle hergeleitet.  
  
- Attribute werden als Spalten hergeleitet.  
  
- Elemente, die keine Attribute oder untergeordnete Elemente aufweisen und sich nicht wiederholen, werden als Spalten hergeleitet.  
  
- Für Elemente, die als geschachtelte Tabellen innerhalb anderer Elemente abgeleitet werden, die auch als Tabellen abgeleitet werden, wird eine geschachtelte **DataRelations** -Beziehung zwischen den beiden Tabellen erstellt. Eine neue Primärschlüssel Spalte mit dem Namen **TableName_Id** wird beiden Tabellen hinzugefügt und von der **DataRelations**verwendet. Eine fremd **Schlüssel Einschränkung** wird zwischen den beiden Tabellen mithilfe der **TableName_Id** -Spalte erstellt.  
  
- Für Elemente, die als Tabellen abgeleitet werden und Text enthalten, aber keine untergeordneten Elemente enthalten, wird für den Text der einzelnen Elemente eine neue Spalte mit dem Namen **TableName_Text** erstellt. Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.  
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines DataSet aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
