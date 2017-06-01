---
title: "Vorgehensweise: Darstellen von Spalten als datenbankgeneriert | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Darstellen von Spalten als datenbankgeneriert
Verwenden Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>\-Eigenschaft des <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attributs, um ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte zu kennzeichnen.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>\-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut hinzu.  
  
2.  Legen Sie den Wert der Eigenschaft auf `true` fest.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)