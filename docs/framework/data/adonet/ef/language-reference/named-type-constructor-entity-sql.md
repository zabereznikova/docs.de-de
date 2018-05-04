---
title: Konstruktoren benannter Typen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: 9ffaf55ed54e8479a56e6f9fc4d7a5efe47f8e2a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="named-type-constructor-entity-sql"></a>Konstruktoren benannter Typen (Entity SQL)
Wird verwendet, um Instanzen von nominalen (EDM)-Typen eines konzeptionellen Modells, wie Entitätstypen oder komplexe Typen zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Argumente  
 `identifier`  
 Wert, der ein einfacher Bezeichner oder ein Bezeichner in Anführungszeichen ist. Weitere Informationen finden Sie unter [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 `expression`  
 Attribute des Typs, deren Reihenfolge mit der in der Deklaration des Typs übereinstimmen sollte.  
  
## <a name="return-value"></a>Rückgabewert  
 Instanzen benannter komplexer Typen und Entitätstypen.  
  
## <a name="remarks"></a>Hinweise  
 In den folgenden Beispielen wird gezeigt, wie nominale und komplexe Typen erstellt werden:  
  
 Mit dem folgenden Ausdruck wird eine Instanz des `Person` -Typs erstellt:  
  
 `Person("abc", 12)`  
  
 Mit dem folgenden Ausdruck wird eine Instanz eines komplexen Typs erstellt:  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 Mit dem folgenden Ausdruck wird eine Instanz eines geschachtelten komplexen Typs erstellt:  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 Mit dem folgenden Ausdruck wird eine Instanz einer Entität mit einem geschachtelten komplexen Typ erstellt:  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 Im folgenden Beispiel wird gezeigt, wie eine Eigenschaft eines komplexen Typs mit NULL initialisiert wird:`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der Konstruktor benannter Typen verwendet, um eine Instanz eines konzeptionellen Modelltyps zu erstellen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a>Siehe auch  
 [Konstruktionstypen](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
