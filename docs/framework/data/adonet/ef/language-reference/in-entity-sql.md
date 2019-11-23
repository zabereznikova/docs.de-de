---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: e46db63600b6baa03697615a2f5eb9240f55d15e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833691"
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Argumente  
 `value`  
 Jeder gültige Ausdruck, der den auf Übereinstimmung zu prüfenden Wert zurückgibt.  
  
 [ NOT ]  
 Legt fest, dass das `Boolean`-Ergebnis von {2}IN{3} negiert werden soll.  
  
 `expression`  
 Jeder gültige Ausdruck, der die auf Übereinstimmung zu prüfende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `value`.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn der Wert in der Auflistung gefunden wird. NULL, wenn der Wert NULL ist oder die Auflistung NULL ist. Andernfalls `false`. Mit NOT IN wird das Ergebnis von IN negiert.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den IN-Operator, um zu bestimmen, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
