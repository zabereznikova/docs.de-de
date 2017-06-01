---
title: "Nicht unterst&#252;tzte Ausdr&#252;cke (Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Nicht unterst&#252;tzte Ausdr&#252;cke (Entity SQL)
In diesem Thema werden [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]\-Ausdrücke beschrieben, die nicht in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt werden. Weitere Informationen finden Sie unter [Die Unterschiede zwischen Entity SQL und Transact\-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).  
  
## Quantifizierte Prädikate  
 In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] sind Konstrukte der folgenden Form zulässig:  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt solche Konstrukte jedoch nicht.  In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können gleichwertige Ausdrücke wie folgt geschrieben werden:  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## Operator \*  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] unterstützt die Verwendung des "\*"\-Operators in der **SELECT**\-Klausel, um anzugeben, dass alle Spalten herausprojiziert werden sollen.  Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.  
  
## Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [Die Unterschiede zwischen Entity SQL und Transact\-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)