---
title: "Parameter (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Parameter (Entity SQL)
Parameter sind Variablen, die außerhalb von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert werden, üblicherweise über eine Bindungs\-API, die von einer Hostsprache verwendet wird.  Jeder Parameter hat einen Namen und einen Typ.  Parameternamen werden in Abfrageausdrücken mit dem at\-Symbol \(@\) als Präfix definiert. Dadurch sind sie von den Namen von Eigenschaften oder anderen Namen, die in der Abfrage definiert sind, unterscheidbar.  
  
 Die Bindungs\-API der Hostsprache stellt APIs für die Parameterbindung zur Verfügung.  
  
## Beispiel  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)