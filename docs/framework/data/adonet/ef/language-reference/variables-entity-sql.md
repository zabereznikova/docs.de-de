---
title: "Variablen (Entity SQL) | Microsoft Docs"
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
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Variablen (Entity SQL)
## Variable  
 Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck.  Ein Variablenverweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Bezeichner gemäß der Definition in [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) sein.  
  
 Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt.  Der Buchstabe `c` in der **FROM**\-Klausel ist die Definition der Variablen.  Die Verwendung von `c` in der **SELECT**\-Klausel stellt den Variablenverweis dar.  
  
```  
select c   
from LOB.customers as c  
```  
  
## Siehe auch  
 [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)   
 [Parameter](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)   
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)