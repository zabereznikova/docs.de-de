---
title: "EXCEPT (Entity SQL) | Microsoft Docs"
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
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# EXCEPT (Entity SQL)
Gibt eine Auflistung der vom Abfrageausdruck auf der linken Seite des EXCEPT\-Operanden zurückgegebenen und unterschiedlichen Werte zurück, die nicht zusätzlich vom Abfrageausdruck auf der rechten Seite des EXCEPT\-Operanden zurückgegeben werden. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.  
  
## Syntax  
  
```  
  
expression EXCEPT expression  
```  
  
## Argumente  
 `expression`  
 Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.  
  
## Rückgabewert  
 Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.  
  
## Hinweise  
 EXCEPT ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren werden von links nach rechts ausgewertet. In der folgenden Tabelle wird die Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren dargestellt.  
  
|Rangfolge|Operatoren|  
|---------------|----------------|  
|Höchste|INTERSECT|  
||UNION<br /><br /> UNION ALL|  
||EXCEPT|  
|Niedrigste|EXISTS<br /><br /> OVERLAPS<br /><br /> FLATTEN<br /><br /> SET|  
  
## Beispiel  
 In der folgenden Entity SQL\-Abfrage wird ein EXCEPT\-Operator verwendet, um eine Auflistung aller unterschiedlicher Werte von zwei Abfrageausdrücken zurückzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)