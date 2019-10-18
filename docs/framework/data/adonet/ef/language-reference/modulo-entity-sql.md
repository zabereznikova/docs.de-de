---
title: Modulo (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 4bbdbe53403cfec2568cfac320fc7ab1ad2725b0
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319601"
---
# <a name="modulo-entity-sql"></a>Modulo (Entity SQL)
Gibt den Rest der Division eines Ausdrucks durch einen anderen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a>Argumente  
 `dividend`  
 Der zu dividierende numerische Ausdruck. `dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.  
  
 `divisor`  
 Der numerische Ausdruck, durch den der Dividend geteilt werden soll. `divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.  
  
## <a name="result-types"></a>Ergebnistypen  
 Edm.Int32  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "%", um den Rest der Division eines Ausdrucks durch einen anderen zurückzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
