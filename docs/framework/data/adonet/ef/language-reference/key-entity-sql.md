---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 14c0b5d273b26c71c9c63e8bbbcef863ac95a5f3
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319699"
---
# <a name="key-entity-sql"></a>KEY (Entity SQL)
Extrahiert den Schlüssel eines Verweises oder eines Entitätsausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Entitätsschlüssel enthält in korrekter Reihenfolge die Schlüsselwerte der angegebenen Entität oder des Entitätsverweises. Da viele Entitätenmengen auf demselben Typ basieren können, kann derselbe Schlüssel in jeder Entitätenmenge vorhanden sein. Um einen eindeutigen Verweis abzurufen, verwenden Sie `REF`. Der Rückgabetyp des KEY-Operators ist ein Zeilentyp, der ein Feld für jeden Schlüssel der Entität in der gleichen Reihenfolge beinhaltet.  
  
 Im folgenden Beispiel wird dem KEY-Operator ein Verweis auf die BadOrder-Entität übergeben, und er gibt den Schlüsselteil dieses Verweises zurück. In diesem Fall einen Datensatztyp mit genau einem Feld, das der `Id` -Eigenschaft entspricht.  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den KEY-Operator, um den Schlüsselteil eines Ausdrucks mit Typverweis zu extrahieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [CREATEREF](createref-entity-sql.md)
- [REF](ref-entity-sql.md)
- [DEREF](deref-entity-sql.md)
