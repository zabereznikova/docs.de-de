---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: ff79417008b7807fbf206d4bcb65b4e5ea1cc576
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296133"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)
Extrahiert ein Element aus einer mehrwertigen Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige, eine Auflistung zurückgebende Abfrageausdruck, aus der ein Element extrahiert werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein einzelnes Element in der Auflistung oder ein beliebiges Element, sofern die Auflistung über verschiedene Elemente verfügt. Wenn die Auflistung leer ist, wird `null`zurückgegeben. Wenn `collection` ist eine Sammlung vom Typ `Collection<T>`, klicken Sie dann `ANYELEMENT(collection)` ist ein gültiger Ausdruck, der eine Instanz des Typs ergibt `T`.  
  
## <a name="remarks"></a>Hinweise  
 ANYELEMENT extrahiert ein beliebiges Element aus einer mehrwertigen Auflistung. Im folgenden Beispiel soll ein Singleton-Element aus dem Satz `Customers`extrahiert werden.  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Beispiel  
 Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage extrahiert mithilfe des ANYELEMENT-Operators ein Element aus einer mehrwertigen Auflistung. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Strukturierte Typen, die NULL-Werte zulassen](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
