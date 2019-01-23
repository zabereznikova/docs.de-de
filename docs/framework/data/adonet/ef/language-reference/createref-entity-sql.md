---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: bdf1c34f8a050764e8f8766da25076a7c1c361ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505080"
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)
Erstellt Verweise auf eine Entität in einer Entitätenmenge.  
  
## <a name="syntax"></a>Syntax  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>Argumente  
 `entityset_identifier`  
 Der Entitätenmengenbezeichner, kein Zeichenfolgenliteral.  
  
 `row_typed_expression`  
 Ein zeilentypisierter Ausdruck, der den Schlüsseleigenschaften des Entitätstyps entspricht.  
  
## <a name="remarks"></a>Hinweise  
 `row_typed_expression` muss strukturell dem Schlüsseltyp der Entität entsprechen. Dies bedeutet, er muss hinsichtlich Anzahl, Typen und Reihenfolge der Felder zu den Entitätsschlüsseln passen.  
  
 Im folgenden Beispiel sind sowohl "Orders" als auch "BadOrders" Entitätenmengen vom Typ "Order". "Id" ist die einzige Schlüsseleigenschaft von "Order". Im Beispiel wird veranschaulicht, wie in "BadOrders" ein Verweis auf eine Entität erstellt werden kann. Beachten Sie, dass der Verweis möglicherweise „hängt“.  Dies bedeutet, dass der Verweis möglicherweise keine spezifische Entität identifiziert. In diesen Fällen gibt eine `DEREF` -Operation auf diesen Verweis den Wert NULL zurück.  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage werden mithilfe des CREATEREF-Operators Verweise auf eine Entität in einer Entitätenmenge erstellt. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a>Siehe auch
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
- [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
