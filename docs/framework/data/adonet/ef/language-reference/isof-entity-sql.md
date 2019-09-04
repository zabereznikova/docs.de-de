---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 3b746a82f72fc7f42f9d91ddd0a7d6f4f86ac0bb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250575"
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
  
 NICHT  
 Negiert das EDM.Boolean-Ergebnis von IS OF.  
  
 ONLY  
 Legt fest, dass von IS OF`true` nur dann `expression` zurückgegeben wird, wenn `type` vom Typ  und nicht von einem seiner Untertypen ist.  
  
 `type`  
 Der Typ, dessen Übereinstimmung mit dem Typ von `expression` überprüft werden soll. Der Typ muss mit einem Namespace qualifiziert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn `expression` vom Typ "T" und "T" entweder ein Basistyp oder ein von `type` abgeleiteter Typ ist. NULL, wenn `expression` zur Laufzeit den Wert NULL hat, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die Ausdrücke `expression IS NOT OF (type)` und `expression IS NOT OF (ONLY type)` `NOT (expression IS OF (type))` sind`NOT (expression IS OF (ONLY type))`syntaktisch Äquivalent zu bzw.  
  
 In der folgenden Tabelle wird das Verhalten des `IS OF`-Operators für einige typische und weniger typische Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|-------------|--------------|  
|null IS OF (EntityType)|Löst aus|  
|null IS OF (ComplexType)|Löst aus|  
|null IS OF (RowType)|Löst aus|  
|TREAT (null AS EntityType) IS OF (EntityType)|Gibt DBNull zurück.|  
|TREAT (null AS ComplexType) IS OF (ComplexType)|Löst aus|  
|TREAT (null AS RowType) IS OF (RowType)|Löst aus|  
|EntityType IS OF (EntityType)|Gibt True/False zurück.|  
|ComplexType IS OF (ComplexType)|Löst aus|  
|RowType IS OF (RowType)|Löst aus|  
  
## <a name="example"></a>Beispiel  
 In der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] folgenden-Abfrage wird der is of-Operator verwendet, um den Typ eines Abfrage Ausdrucks zu ermitteln. Anschließend wird der Treat-Operator verwendet, um ein Objekt des Typs "Kurs" in eine Auflistung von Objekten des Typs "OnsiteCourse" zu konvertieren. Die Abfrage basiert auf dem [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
