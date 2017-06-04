---
title: "Operatorrangfolge (Entity SQL) | Microsoft Docs"
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
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Operatorrangfolge (Entity SQL)
Wenn in einer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Abfrage mehrere Operatoren vorkommen, bestimmt die Operatorrangfolge die Reihenfolge, in der die einzelnen Operationen durchgeführt werden.  Die Ausführungsreihenfolge kann sich entscheidend auf das Abfrageergebnis auswirken.  
  
 Operatoren besitzen die in der folgenden Tabelle dargestellte Rangfolge.  Ein Operator, der höher in der Rangfolge steht, wird vor einem Operator niedrigeren Ranges ausgewertet.  
  
|Ebene|Operationstyp|Operator|  
|-----------|-------------------|--------------|  
|1|Primär|`. , [] ()`|  
|2|Unär|`! not`|  
|3|Multiplikativ|`* / %`|  
|4|Additiv|`+ -`|  
|5|Sortieren|`< > <= >=`|  
|6|Gleichheit|`= != <>`|  
|7|Bedingtes AND|`and &&`|  
|8|Bedingtes OR|`or &#124;&#124;`|  
  
 Verfügen zwei Operatoren in einem Ausdruck über die gleiche Rangstufe, werden sie von links nach rechts, ausgehend von ihrer Position innerhalb der Abfrage, ausgewertet.   `x+y-z`  wird beispielsweise als  `(x+y)-z` ausgewertet.  
  
 Mit Klammern kann die definierte Rangfolge von Operatoren in einer Abfrage außer Kraft gesetzt werden.  Die Operatoren innerhalb der Klammern werden zuerst ausgewertet, bevor das sich ergebende einzelne Ergebnis von den Operatoren außerhalb der Klammern verwendet werden kann.  Zum Beispiel wird bei `x+y*z`  `y` mit `z` multipliziert und dann `x` addiert, bei `(x+y)*z` wird jedoch `x` zu `y` addiert und dann das Ergebnis mit `z` multipliziert.  
  
## Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)