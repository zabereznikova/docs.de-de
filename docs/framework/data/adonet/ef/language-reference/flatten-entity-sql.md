---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 897a5071e45fb92d6a5cc4d44c7a7efc0606f745
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702196"
---
# <a name="flatten-entity-sql"></a>FLATTEN (Entity SQL)
Konvertiert eine Auflistung von Auflistungen in eine vereinfachte Auflistung. Die neue Auflistung enthält dieselben Elemente wie die alte Auflistung, jedoch ohne geschachtelte Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Argumente  
 `collection`  
 Jeder gültige Ausdruck, der eine zu einer einzigen Auflistung zu vereinfachende Auflistung von Werten zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 `FLATTEN` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set-Operatoren.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den `FLATTEN` -Operator, um eine Auflistung von Auflistungen in eine vereinfachte Auflistung zu konvertieren. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a>Siehe auch
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
