---
title: "&amp;&amp; (AND) (Entity SQL) | Microsoft Docs"
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
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &amp;&amp; (AND) (Entity SQL)
Gibt `true` zurück, wenn beide Ausdrücke `true` sind, andernfalls `false` oder `NULL`.  
  
## Syntax  
  
```  
  
          boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## Argumente  
 `boolean_expression`  
 Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.  
  
## Hinweise  
 Zwei kaufmännische Und\-Zeichen \(&&\) haben dieselbe Bedeutung wie der AND\-Operator.  
  
 In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|FALSE|NULL|  
|`FALSE`|FALSE|FALSE|FALSE|  
|`NULL`|NULL|FALSE|NULL|  
  
## Beispiel  
 In der folgenden Entity SQL\-Abfrage wird die Verwendung des AND\-Operators veranschaulicht. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)