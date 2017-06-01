---
title: "Vorgehensweise: Angeben von Datenbanknamen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Angeben von Datenbanknamen
Verwenden Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>\-Eigenschaft für ein <xref:System.Data.Linq.Mapping.DatabaseAttribute>\-Attribut, um den Namen einer Datenbank anzugeben, wenn dieser nicht von der Verbindung bereitgestellt wird.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### So geben Sie den Namen der Datenbank an  
  
1.  Fügen Sie das <xref:System.Data.Linq.Mapping.DatabaseAttribute>\-Attribut der Klassendeklaration für die Datenbank hinzu.  
  
2.  Fügen Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>\-Eigenschaft dem <xref:System.Data.Linq.Mapping.DatabaseAttribute>\-Attribut hinzu.  
  
3.  Legen Sie den <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>\-Eigenschaftswert auf den gewünschten Namen fest.  
  
## Siehe auch  
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)