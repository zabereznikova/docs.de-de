---
title: "OVERLAPS (Entity SQL) | Microsoft Docs"
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
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# OVERLAPS (Entity SQL)
Bestimmt, ob zwei Auflistungen über gemeinsame Elemente verfügen.  
  
## Syntax  
  
```  
  
expression OVERLAPS expression  
```  
  
## Argumente  
 `expression`  
 Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.  
  
## Rückgabewert  
 `true`, wenn die beiden Auflistungen gemeinsame Elemente aufweisen, andernfalls `false`.  
  
## Hinweise  
 Die von OVERLAPS bereitgestellten Funktionen entsprechen Folgendem:``  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren werden von links nach rechts ausgewertet. Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## Beispiel  
 Die folgende Entity SQL\-Abfrage verwendet den OVERLAPS\-Operator, um zu bestimmen, ob zwei Auflistungen einen gemeinsamen Wert haben. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)