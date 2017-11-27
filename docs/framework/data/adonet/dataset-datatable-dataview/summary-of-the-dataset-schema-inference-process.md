---
title: "Zusammenfassung des Rückschlussprozesses von DataSet-Schemas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15469e917129db7668df17f22fb71b166993d4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
-   Für Elemente, die als geschachtelte Tabellen innerhalb von anderen Elementen abgeleitet werden, die auch abgeleitet werden als Tabellen, eine geschachtelte **DataRelation** wird zwischen den beiden Tabellen erstellt. Eine neue Primärschlüsselspalte mit dem Namen **TableName_Id** für beide Tabellen hinzugefügt und verwendet werden, indem Sie die **DataRelation**. Ein **ForeignKeyConstraint** wird erstellt, zwischen den beiden Tabellen mithilfe der **TableName_Id** Spalte.  
  
-   Für Elemente, die als Tabellen hergeleitet werden, und, die Text enthalten, aber keine untergeordneten Elemente besitzen, eine neue Spalte mit dem Namen **TableName_Text** wird für den Text aller Elemente erstellt. Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.  
  
## <a name="see-also"></a>Siehe auch  
 [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Beim Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Beim Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
