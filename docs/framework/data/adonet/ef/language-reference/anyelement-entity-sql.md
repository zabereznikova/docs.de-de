---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: e060956545ca924fa6fedb80b2f53ff312f307a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201199"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)

Extrahiert ein Element aus einer mehrwertigen Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Jeder gültige, eine Auflistung zurückgebende Abfrageausdruck, aus der ein Element extrahiert werden soll.  
  
## <a name="return-value"></a>Rückgabewert  

 Ein einzelnes Element in der Auflistung oder ein beliebiges Element, sofern die Auflistung über verschiedene Elemente verfügt. Wenn die Auflistung leer ist, wird `null`zurückgegeben. Wenn `collection` eine Auflistung vom Typ ist `Collection<T>` , dann `ANYELEMENT(collection)` ist ein gültiger Ausdruck, der eine Instanz vom Typ ergibt `T` .  
  
## <a name="remarks"></a>Bemerkungen  

 ANYELEMENT extrahiert ein beliebiges Element aus einer mehrwertigen Auflistung. Im folgenden Beispiel soll ein Singleton-Element aus dem Satz `Customers`extrahiert werden.  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Beispiel  

 Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage extrahiert mithilfe des ANYELEMENT-Operators ein Element aus einer mehrwertigen Auflistung. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Strukturierte Typen, die NULL-Werte zulassen](nullable-structured-types-entity-sql.md)
