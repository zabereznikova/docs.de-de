---
title: "Vorgehensweise: Darstellen von berechneten Spalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Darstellen von berechneten Spalten
Verwenden Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>\-Eigenschaft des <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attributs für die Darstellung einer Spalte, deren Inhalt das Ergebnis einer Berechnung ist.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt keine berechneten Spalten als Primärschlüssel.  
  
### So stellen Sie eine berechnete Spalte dar  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>\-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut hinzu.  
  
2.  Weisen Sie der <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>\-Eigenschaft eine Zeichenfolgendarstellung der Formel zu.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)