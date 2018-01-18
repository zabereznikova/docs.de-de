---
title: TREAT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 65b5a67ffa910841d825adc729990d365ac50357
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="treat-entity-sql"></a>TREAT (Entity SQL)
Behandelt ein Objekt eines bestimmten Basistyps als Objekt des angegebenen abgeleiteten Typs.  
  
## <a name="syntax"></a>Syntax  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Entität zurückgibt.  
  
> [!NOTE]
>  Beim Typ des angegebenen Ausdrucks muss es sich um einen Untertyp des angegebenen Datentyps oder umgekehrt handeln.  
  
 `type`  
 Ein Entitätstyp. Der Typ muss mit einem Namespace qualifiziert werden.  
  
> [!NOTE]
>  Beim Typ des angegebenen Ausdrucks muss es sich um einen Untertyp des angegebenen Datentyps oder umgekehrt handeln.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Wert des angegebenen Datentyps.  
  
## <a name="remarks"></a>Hinweise  
 TREAT wird zum Umwandeln zwischen verknüpften Klassen verwendet. Wenn z. B. `Employee` von `Person` abgeleitet ist und "p" vom Typ `Person`ist, wandelt `TREAT(p AS NamespaceName.Employee)` eine generische `Person` -Instanz in `Employee`um. Das bedeutet, dass "p" als `Employee`behandelt werden kann.  
  
 TREAT wird in Vererbungsszenarios verwendet, in denen eine Abfrage wie die folgende möglich ist:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 In dieser Abfrage werden `Person` -Entitäten in den `Employee` -Typ umgewandelt. Wenn der Wert von "p" nicht tatsächlich vom Typ `Employee`ist, gibt der Ausdruck den Wert `null`zurück.  
  
> [!NOTE]
>  Der angegebene Ausdruck `Employee` muss sich um einen Untertyp des angegebenen Datentyps `Person`, oder der Datentyp muss es sich um einen Untertyp des Ausdrucks. Andernfalls führt der Ausdruck zu einem Kompilierungsfehler.  
  
 In der folgenden Tabelle wird das Verhalten von TREAT für einige typische und weniger typische Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|Gibt `DbNull`zurück.|  
|`TREAT (null AS ComplexType)`|Löst eine Ausnahme aus.|  
|`TREAT (null AS RowType)`|Löst eine Ausnahme aus.|  
|`TREAT (EntityType AS EntityType)`|Gibt einen `EntityType` oder `null`zurück.|  
|`TREAT (ComplexType AS ComplexType)`|Löst eine Ausnahme aus.|  
|`TREAT (RowType AS RowType)`|Löst eine Ausnahme aus.|  
  
## <a name="example"></a>Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der TREAT-Operator verwendet, um ein Objekt des Typs "Kurs" in eine Auflistung von Objekten des Typs "OnsiteCourse" umzuwandeln. Die Abfrage basiert auf dem [Modell "School"](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Strukturierte Typen, die NULL-Werte zulassen](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
