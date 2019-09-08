---
title: Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: b0dd22412ddda86aa2883a26353abb1516a94e17
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785946"
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
- [Übersicht über ADO.NET](../ado-net-overview.md)
