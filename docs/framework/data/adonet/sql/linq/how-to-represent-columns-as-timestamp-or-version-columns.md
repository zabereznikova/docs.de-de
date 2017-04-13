---
title: "Vorgehensweise: Darstellen von Spalten als Timestamp- oder Versionsspalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Darstellen von Spalten als Timestamp- oder Versionsspalten
Verwenden Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>\-Eigenschaft des <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attributs, um ein Feld oder eine Eigenschaft für die Darstellung einer Datenbankspalte zu kennzeichnen, die Datenbank\-Timestamps oder \-Versionsnummern enthält.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer Timestamp\- oder Versionsspalte  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>\-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut hinzu.  
  
2.  Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>\-Eigenschaftswert auf `true` fest.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)