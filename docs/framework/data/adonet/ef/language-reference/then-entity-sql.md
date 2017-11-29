---
title: THEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 99fd941c963ff87203d7b315beb606d40001224d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Das Ergebnis einer WHEN-Klausel, wenn sie als `true`ausgewertet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argumente  
 `when_expression`  
 Jeder gültige boolesche Ausdruck.  
  
 `then_expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Falls `when_expression` zum Wert `true`ausgewertet wird, ist das Ergebnis der entsprechende `then-expression`. Wird keine der WHEN-Bedingungen erfüllt, wird der `else-expression` ausgewertet. Wenn jedoch kein `else-expression`vorhanden ist, ist das Ergebnis NULL.  
  
 Ein Beispiel finden Sie unter [Fall](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung einer Reihe von `Boolean` -Ausdrücken verwendet. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Siehe auch  
 [FALL](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
