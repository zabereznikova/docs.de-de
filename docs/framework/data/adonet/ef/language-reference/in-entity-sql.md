---
title: "IN (Entity SQL) | Microsoft Docs"
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
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# IN (Entity SQL)
Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.  
  
## Syntax  
  
```  
  
value [ NOT ] IN expression  
```  
  
## Argumente  
 `value`  
 Jeder gültige Ausdruck, der den auf Übereinstimmung zu prüfenden Wert zurückgibt.  
  
 \[ NOT \]  
 Legt fest, dass das `Boolean`\-Ergebnis von IN negiert werden soll.  
  
 `expression`  
 Jeder gültige Ausdruck, der die auf Übereinstimmung zu prüfende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `value`.  
  
## Rückgabewert  
 `true`, wenn der Wert in der Auflistung gefunden wurde, null, wenn der Wert oder die Auflistung NULL ist, anderenfalls `false`. Mit NOT IN wird das Ergebnis von IN negiert.  
  
## Beispiel  
 Die folgende Entity SQL\-Abfrage verwendet den IN\-Operator, um zu bestimmen, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)