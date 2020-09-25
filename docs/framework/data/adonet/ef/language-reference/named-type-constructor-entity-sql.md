---
title: Konstruktoren benannter Typen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c673b58ee5811e3d3b74b3744d3f5291888e2253
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197780"
---
# <a name="named-type-constructor-entity-sql"></a>Konstruktoren benannter Typen (Entity SQL)

Wird verwendet, um Instanzen von nominalen (EDM)-Typen eines konzeptionellen Modells, wie Entitätstypen oder komplexe Typen zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Argumente  

 `identifier`  
 Wert, der ein einfacher Bezeichner oder ein Bezeichner in Anführungszeichen ist. Weitere Informationen finden [Sie unter](identifiers-entity-sql.md) Bezeichner.  
  
 `expression`  
 Attribute des Typs, deren Reihenfolge mit der in der Deklaration des Typs übereinstimmen sollte.  
  
## <a name="return-value"></a>Rückgabewert  

 Instanzen benannter komplexer Typen und Entitätstypen.  
  
## <a name="remarks"></a>Bemerkungen  

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
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Konstruktionstypen](constructing-types-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
