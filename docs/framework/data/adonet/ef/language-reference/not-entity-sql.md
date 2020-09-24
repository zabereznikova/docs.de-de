---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0eb9be9ed4cbce45a51d15eea68e9fb1a26f0107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191839"
---
# <a name="-not-entity-sql"></a>! (NOT) (Entity SQL)

Negiert einen `Boolean` -Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a>Argumente  

 `boolean_expression`  
 Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.  
  
## <a name="remarks"></a>Bemerkungen  

 Das Ausrufezeichen (!) hat dieselbe Bedeutung wie der NOT-Operator.  
  
## <a name="example"></a>Beispiel  

 Die folgende Entity SQL-Abfrage verwendet den NOT-Operator, um einen `Boolean` -Ausdruck zu negieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
