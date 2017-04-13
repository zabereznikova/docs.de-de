---
title: "LIMIT (Entity SQL) | Microsoft Docs"
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
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LIMIT (Entity SQL)
Das physische Paging kann mit LIMIT\-Unterklauseln in der ORDER BY\-Klausel durchgeführt werden. LIMIT kann nicht ohne ORDER BY\-Klausel verwendet werden.  
  
## Syntax  
  
```  
  
[ LIMIT n ]  
```  
  
## Argumente  
 `n`  
 Die Anzahl der auszuwählenden Elemente.  
  
 Wenn eine ORDER BY\-Klausel den Ausdruck LIMIT als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den LIMIT\-Ausdruck begrenzt. LIMIT 5 z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen. Die Funktionsweise von LIMIT entspricht der von TOP, mit dem Unterschied, dass LIMIT nur mit einer ORDER BY\-Klausel verwendet werden kann. SKIP und LIMIT können zusammen mit einer ORDER BY\-Klausel voneinander unabhängig verwendet werden.  
  
> [!NOTE]
>  Eine Entity Sql\-Abfrage gilt als ungültig, wenn im selben Abfrageausdruck ein TOP\-Modifizierer und eine SKIP\-Unterklausel vorhanden sind. Die Abfrage sollte umgeschrieben werden, indem der TOP\-Ausdruck in einen LIMIT\-Ausdruck geändert wird.  
  
## Beispiel  
 In der folgenden Entity SQL\-Abfrage wird der ORDER BY\-Operator mit LIMIT verwendet, um für die von der SELECT\-Anweisung zurückgegebenen Objekte die zu verwendende Sortierreihenfolge anzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## Siehe auch  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)   
 [Gewusst wie: Seitenweise durch Abfrageresultate navigieren](http://msdn.microsoft.com/de-de/ffc0f920-e7de-42e0-9b12-ef356421d030)   
 [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)   
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)