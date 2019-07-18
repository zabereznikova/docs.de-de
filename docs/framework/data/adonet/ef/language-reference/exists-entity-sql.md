---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 72d96c5f24fcedf870370de3792680831145a454
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034202"
---
# <a name="exists-entity-sql"></a>EXISTS (Entity SQL)
Bestimmt, ob eine Auflistung leer ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Ausdruck, der eine Auflistung zurückgibt.  
  
 NICHT  
 Gibt an, dass das Ergebnis von EXISTS negiert werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Auflistung nicht leer ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 EXISTS[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist einer der -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengenoperatoren, finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den EXISTS-Operator, um festzustellen, ob die Auflistung leer ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
