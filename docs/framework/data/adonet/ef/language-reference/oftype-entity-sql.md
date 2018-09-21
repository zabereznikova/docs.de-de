---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: c90950e11cbfca7a49b505c1654d08be504990e1
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46536966"
---
# <a name="oftype-entity-sql"></a>OFTYPE (Entity SQL)
Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung von Objekten zurückgibt.  
  
 `test_type`  
 Der Typ, dessen Übereinstimmung mit jedem von `expression` zurückgegebenen Objekt getestet wird. Der Typ muss mit einem Namespace qualifiziert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung von Objekten vom Typ `test_type`, von einem Basistyp oder von einem von `test_type`abgeleiteten Typ. Wenn ONLY angegeben wird, werden nur Instanzen des `test_type` oder eine leere Auflistung zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Ein `OFTYPE` -Ausdruck stellt einen Typausdruck dar, der angegeben wird, um einen Typtest für jedes Element einer Auflistung durchzuführen.  Der `OFTYPE` -Ausdruck liefert eine neue Auflistung des angegebenen Typs, die nur die zu diesem Typ oder einem seiner Untertypen äquivalenten Elemente enthält.  
  
 Ein `OFTYPE` -Ausdruck ist eine Abkürzung des folgenden Abfrageausdrucks:  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 Wenn beispielsweise "Manager" ein Untertyp von "Employee" (Mitarbeiter) ist, liefert der folgende Ausdruck nur die Manager aus einer Auflistung der Mitarbeiter:  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 Mithilfe des Typfilters kann eine Auflistung auch umgewandelt werden:  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 Da alle Direktoren Manager sind, enthält die resultierende Auflistung alle Direktoren, auch wenn die Auflistung nun als eine Auflistung von Managern typisiert ist.  
  
 In der folgenden Tabelle wird das Verhalten des `OFTYPE` -Operators für verschiedene Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|-------------|--------------|  
|OFTYPE (Collection(EntityType), (EntityType)|Collection(EntityType)|  
|OFTYPE(Collection(ComplexType), ComplexType)|Löst aus|  
|OFTYPE(Collection(RowType), RowType)|Löst aus|  
  
## <a name="example"></a>Beispiel  
 Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage verwendet den OFTYPE-Operator, um eine Auflistung der OnsiteCourse-Objekte von einer Auflistung von Kursobjekten zurückzugeben. Die Abfrage basiert auf der [Modell "School"](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
