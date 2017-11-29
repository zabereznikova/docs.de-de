---
title: '!= (Ungleich) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a2187e317229961b0929f1415cd40f6f65f5c593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="-not-equal-to-entity-sql"></a>!= (Ungleich) (Entity SQL)
Vergleicht zwei Ausdrücke, um zu ermitteln, ob sich der linke Ausdruck vom rechten Ausdruck unterscheidet. Die Funktionsweise des Operators "!=" (Ungleich) ist dieselbe wie die des Operators <>.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Ausdruck. Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.  
  
## <a name="result-types"></a>Ergebnistypen  
 `true` , wenn der linke Ausdruck ungleich dem rechten Ausdruck ist, andernfalls `false`.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der Operator "!=" verwendet, um zu ermitteln, ob der linke Ausdruck ungleich dem rechten Ausdruck ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
