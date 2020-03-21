---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 06c4200434f443446e8981dcefe2baf43b1af4b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149894"
---
# <a name="treat-entity-sql"></a>TREAT (Entity SQL)
Behandelt ein Objekt eines bestimmten Basistyps als Objekt des angegebenen abgeleiteten Typs.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Entität zurückgibt.  
  
> [!NOTE]
> Beim Typ des angegebenen Ausdrucks muss es sich um einen Untertyp des angegebenen Datentyps oder umgekehrt handeln.  
  
 `type`  
 Ein Entitätstyp. Der Typ muss mit einem Namespace qualifiziert werden.  
  
> [!NOTE]
> Beim Typ des angegebenen Ausdrucks muss es sich um einen Untertyp des angegebenen Datentyps oder umgekehrt handeln.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Wert des angegebenen Datentyps.  
  
## <a name="remarks"></a>Bemerkungen  
 TREAT wird zum Umwandeln zwischen verknüpften Klassen verwendet. Wenn z. B. `Employee` von `Person` abgeleitet ist und "p" vom Typ `Person`ist, wandelt `TREAT(p AS NamespaceName.Employee)` eine generische `Person` -Instanz in `Employee`um. Das bedeutet, dass "p" als `Employee`behandelt werden kann.  
  
 TREAT wird in Vererbungsszenarios verwendet, in denen eine Abfrage wie die folgende möglich ist:  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)
```  
  
 In dieser Abfrage werden `Person` -Entitäten in den `Employee` -Typ umgewandelt. Wenn der Wert von "p" nicht tatsächlich vom Typ `Employee`ist, gibt der Ausdruck den Wert `null`zurück.  
  
> [!NOTE]
> Der angegebene `Employee` Ausdruck muss ein Untertyp `Person`des angegebenen Datentyps sein, oder der Datentyp muss ein Untertyp des Ausdrucks sein. Andernfalls führt der Ausdruck zu einem Kompilierungsfehler.  
  
 In der folgenden Tabelle wird das Verhalten von TREAT für einige typische und weniger typische Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|Gibt `DbNull` zurück.|  
|`TREAT (null AS ComplexType)`|Löst eine Ausnahme aus.|  
|`TREAT (null AS RowType)`|Löst eine Ausnahme aus.|  
|`TREAT (EntityType AS EntityType)`|Gibt `EntityType` oder `null` zurück.|  
|`TREAT (ComplexType AS ComplexType)`|Löst eine Ausnahme aus.|  
|`TREAT (RowType AS RowType)`|Löst eine Ausnahme aus.|  
  
## <a name="example"></a>Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der TREAT-Operator verwendet, um ein Objekt des Typs "Kurs" in eine Auflistung von Objekten des Typs "OnsiteCourse" umzuwandeln. Die Abfrage basiert auf dem [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-sql[DP EntityServices Concepts#TREAT_ISOF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Strukturierte Typen, die NULL-Werte zulassen](nullable-structured-types-entity-sql.md)
