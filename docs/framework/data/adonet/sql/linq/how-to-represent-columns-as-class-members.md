---
title: "Vorgehensweise: Darstellen von Spalten als Klassenmember | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Darstellen von Spalten als Klassenmember
Verwenden Sie das [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut, um einer Datenbankspalte ein Feld oder eine Eigenschaft zuzuweisen.  
  
### So ordnen Sie einer Datenbankspalte ein Feld oder eine Eigenschaft zu  
  
-   Fügen Sie das <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut der Eigenschaft oder Felddeklaration hinzu.  
  
## Beispiel  
 Der folgende Code weist das `CustomerID`\-Feld in der `Customer`\-Klasse der `CustomerID`\-Spalte in der `Customers`\-Datenbanktabelle zu.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>\-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann.  Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)