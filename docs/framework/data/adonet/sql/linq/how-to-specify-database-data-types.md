---
title: "Vorgehensweise: Angeben von Datenbankdatentypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Angeben von Datenbankdatentypen
Verwenden Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>\-Eigenschaft des <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attributs, um den genauen Text festzulegen, der die Spalte in einer T\-SQL\-Tabellendeklaration definiert.  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>\-Eigenschaft nur dann angeben, wenn Sie planen, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> zur Erstellung einer Datenbankinstanz einzusetzen.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### So geben Sie Text an, um einen Datentyp in einer T\-SQL\-Tabelle zu definieren  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>\-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut hinzu.  
  
2.  Legen Sie den Wert der <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>\-Eigenschaft auf den genauen Text fest, der von T\-SQL verwendet wird.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)