---
title: "Vorgehensweise: Darstellen von Tabellen als Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Darstellen von Tabellen als Klassen
Verwenden Sie das [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute>\-Attribut, um eine Klasse als Entität zu kennzeichnen, die einer Datenbanktabelle zugeordnet ist.  
  
### So ordnen Sie einer Datenbanktabelle eine Klasse zu  
  
-   Fügen Sie das <xref:System.Data.Linq.Mapping.TableAttribute>\-Attribut der Klassendeklaration hinzu.  
  
## Beispiel  
 Der folgende Code etabliert die `Customer`\-Klasse als eine Entitätsklasse, die der `Customers`\-Datenbanktabelle zugeordnet ist.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>\-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann.  Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)