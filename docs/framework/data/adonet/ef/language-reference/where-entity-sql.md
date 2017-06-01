---
title: "WHERE (Entity SQL) | Microsoft Docs"
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
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# WHERE (Entity SQL)
Die **WHERE**\-Klausel wird direkt nach der [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)\-Klausel angewendet.  
  
## Syntax  
  
```  
[ WHERE expression ]  
```  
  
## Argumente  
 `expression`  
 Ein boolescher Typ.  
  
## Hinweise  
 Die **WHERE**\-Klausel hat die für [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] beschriebene Semantik.  Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.  
  
```  
select c from cs as c where e  
```  
  
 Der Ausdruck `e` muss einen booleschen Wert haben.  
  
 Die **WHERE**\-Klausel wird direkt nach der **FROM**\-Klausel und vor der Ausführung von Gruppierungs\-, Sortierungs\- oder Projektionsvorgängen angewendet.  Alle in der **FROM**\-Klausel definierten Elementnamen sind für den Ausdruck der **WHERE**\-Klausel sichtbar.  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Abfrageausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)