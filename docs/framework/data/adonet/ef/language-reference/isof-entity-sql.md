---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 7aecb8e2740ffd711278bfd5735c71c2dacf9c3c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762139"
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein gültiger Abfrageausdruck, dessen Typ bestimmt werden soll.  
  
 NOT  
 Negiert das EDM.Boolean-Ergebnis von IS OF.  
  
 ONLY  
 Legt fest, dass von IS OF`true` nur dann `expression` zurückgegeben wird, wenn `type` vom Typ  und nicht von einem seiner Untertypen ist.  
  
 `type`  
 Der Typ, dessen Übereinstimmung mit dem Typ von `expression` überprüft werden soll. Der Typ muss mit einem Namespace qualifiziert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn `expression` vom Typ "T" und "T" entweder ein Basistyp oder ein von `type` abgeleiteter Typ ist. NULL, wenn `expression` zur Laufzeit den Wert NULL hat, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die Ausdrücke `expression IS NOT OF (type)` und `expression IS NOT OF (ONLY type)` entsprechen syntaktisch `NOT (expression IS OF (type))` und `NOT (expression IS OF (ONLY type))`zugeordnet.  
  
 In der folgenden Tabelle wird das Verhalten des `IS OF`-Operators für einige typische und weniger typische Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|-------------|--------------|  
|null IS OF (EntityType)|Löst aus|  
|null IS OF (ComplexType)|Löst aus|  
|null IS OF (RowType)|Löst aus|  
|TREAT (null AS EntityType) IS OF (EntityType)|Gibt DBNull zurück.|  
|TREAT (null AS ComplexType) IS OF (ComplexType)|Löst aus|  
|TREAT (null AS RowType) IS OF (RowType)|Löst aus|  
|EntityType IS OF (EntityType)|Gibt true/false zurück|  
|ComplexType IS OF (ComplexType)|Löst aus|  
|RowType IS OF (RowType)|Löst aus|  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage mithilfe des Operators IS OF um den Typ eines Abfrageausdrucks zu ermitteln und dann den TREAT-Operator verwendet, um ein Objekt des Typs Kurs in eine Auflistung von Objekten des Typs "OnsiteCourse" umzuwandeln. Diese Abfrage beruht auf dem [Modell ' School '](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
