---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 582a3b988247f1484197c0905fecf7f4407f88b0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203669"
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
 Legt fest, dass das -Ergebnis von IN negiert werden soll.  
  
 `expression`  
 Jeder gültige Ausdruck, der die auf Übereinstimmung zu prüfende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `value`.  
  
## <a name="return-value"></a>Rückgabewert  

 `true`, wenn der Wert in der Auflistung gefunden wurde, null, wenn der Wert oder die Auflistung NULL ist, anderenfalls `false`. Mit NOT IN wird das Ergebnis von IN negiert.  
  
## <a name="example"></a>Beispiel  

 Die folgende Entity SQL-Abfrage verwendet den IN-Operator, um zu bestimmen, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
