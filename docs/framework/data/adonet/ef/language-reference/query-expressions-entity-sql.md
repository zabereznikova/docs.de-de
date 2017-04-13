---
title: "Abfrageausdr&#252;cke (Entity SQL) | Microsoft Docs"
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
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Abfrageausdr&#252;cke (Entity SQL)
Ein Abfrageausdruck fasst viele verschiedene Abfrageoperatoren in einer einzigen Syntax zusammen.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt verschiedene Arten von Ausdrücken bereit, einschließlich Folgenden: [Literale](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [Parameter](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [Variablen](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), Operatoren, [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), Mengenoperatoren usw.  Weitere Informationen finden Sie unter [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## Klauseln  
 Ein Abfrageausdruck setzt sich aus einer Serie von Klauseln zusammen, die für eine Auflistung von Objekten aufeinander folgende Operationen durchführen.  Sie basieren auf denselben Klauseln, die Sie auch in einer Standard\-SQL\-SELECT\-Anweisung finden: [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) und [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## Umfang  
 In der **FROM**\-Klausel definierte Namen werden in der Reihenfolge ihres Auftretens \(von links nach rechts\) in den **FROM**\-Gültigkeitsbereich eingeführt.  In der **JOIN**\-Liste können Ausdrücke auf Namen verweisen, die zuvor in der Liste definiert wurden.  Öffentliche Eigenschaften von in der **FROM**\-Klausel festgelegten Elementen werden dem **FROM**\-Gültigkeitsbereich nicht hinzugefügt: Auf sie muss immer mit dem aliasqualifizierten Namen verwiesen werden.  Üblicherweise werden im **FROM**\-Gültigkeitsbereich alle Teile des **SELECT**\-Ausdrucks berücksichtigt.  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)