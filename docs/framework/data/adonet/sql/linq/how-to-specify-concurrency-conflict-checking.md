---
title: "Vorgehensweise: Angeben von Parallelit&#228;tskonflikt&#252;berpr&#252;fungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Angeben von Parallelit&#228;tskonflikt&#252;berpr&#252;fungen
Sie können festlegen, welche Datenbankspalten auf Parallelitätskonflikte geprüft werden, wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.  Weitere Informationen finden Sie unter [Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
## Beispiel  
 Der folgende Code gibt an, dass der `HomePage`\-Member nie während der Updateprüfungen getestet werden sollte.  Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)