---
title: 'Gewusst wie: Darstellen von Spalten als datenbankgeneriert'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a0b36e7035b885985e70203146957cdfca92148b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-database-generated"></a>Gewusst wie: Darstellen von Spalten als datenbankgeneriert
Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Eigenschaft auf die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut so kennzeichnen Sie ein Feld oder eine Eigenschaft Darstellung einer datenbankgenerierten Spalte.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2.  Legen Sie den Wert der Eigenschaft auf `true` fest.  
  
## <a name="see-also"></a>Siehe auch  
 [Die LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
