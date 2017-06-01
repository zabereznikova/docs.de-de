---
title: "Paging (Entity SQL) | Microsoft Docs"
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
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Paging (Entity SQL)
Physisches Paging kann durch Verwendung der [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)\-Unterklausel und der [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)\-Unterklausel in der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)\-Klausel durchgeführt werden.  Um physisches Paging deterministisch durchzuführen, sollten Sie **SKIP** und **LIMIT** verwenden.  Wenn Sie nur die Anzahl der Zeilen in einem Ergebnis auf nicht\-deterministische Weise beschränken möchten, sollten Sie [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md) verwenden.  **TOP** und **SKIP**\/**LIMIT** schließen sich gegenseitig aus.  
  
## Übersicht über 'TOP'  
 Der **SELECT**\-Klausel kann hinter dem optionalen **ALL\/DISTINCT**\-Modifizierer eine **TOP**\-Unterklausel angefügt werden.  Die **TOP**\-Unterklausel gibt an, dass nur der erste Zeilensatz aus dem Abfrageergebnis zurückgegeben wird.  Weitere Informationen finden Sie unter [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## Übersicht über 'SKIP' und 'LIMIT'  
 **SKIP** und **LIMIT** sind Teil der **ORDER BY**\-Klausel.  Wenn eine **ORDER BY**\-Klausel den Ausdruck **SKIP** als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den **SKIP**\-Ausdruck folgen.  Mit **SKIP 5** werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben.  Wenn eine **ORDER BY**\-Klausel den Ausdruck **LIMIT** als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den **LIMIT**\-Ausdruck begrenzt.  **LIMIT 5** z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen.  **SKIP** und **LIMIT** müssen nicht gemeinsam verwendet werden; Sie können auch nur **SKIP** oder nur **LIMIT** mit der **ORDER BY**\-Klausel verwenden.  Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [How to: Page Through Query Results](http://msdn.microsoft.com/de-de/ffc0f920-e7de-42e0-9b12-ef356421d030)