---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: bacc773351812a5db60f493f3025c8e4b07dbaa2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833800"
---
# <a name="function-entity-sql"></a>FUNCTION (Entity SQL)
Definiert eine Funktion im Bereich eines Entity SQL-Abfragebefehls.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a>Argumente  
 `function-name`  
 Name der Funktion.  
  
 `parameter-name`  
 Der Name eines Parameters in der Funktion.  
  
 `function_expression`  
 Ein gültiger Entity SQL-Ausdruck, der die Funktion darstellt. Der Befehl in der Funktion kann auf `parameter_name` -Parameter, die an die Funktion übergeben wurden, angewendet werden.  
  
 `data_type`  
 Der Name eines unterstützten Typs.  
  
 COLLECTION ( <type_definition`>` )  
 Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.  
  
 REF **(** `data_type` **)**  
 Ein Ausdruck, der einen Verweis auf einen Entitätstyp zurückgibt.  
  
 ROW **(** `row_expression` **)**  
 Ein Ausdruck, der anonyme strukturell eingegebene Datensätze von mindestens einem Wert zurückgibt. Weitere Informationen finden Sie unter [ROW](row-entity-sql.md).  
  
## <a name="remarks"></a>Hinweise  
 Mehrere Funktionen mit dem gleichen Namen können inline deklariert werden, sofern sie unterschiedliche Funktionssignaturen aufweisen. Weitere Informationen finden Sie unter [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
 Eine Inlinefunktion kann nur in einem Entity SQL-Befehl aufgerufen werden, nachdem sie in diesem Befehl definiert wurde. Eine Inlinefunktion kann jedoch in einer anderen Inlinefunktion aufgerufen werden, bevor oder nachdem die aufgerufene Funktion definiert wurde. Im folgenden Beispiel wird Funktion B von Funktion A aufgerufen, bevor Funktion B definiert wird:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Aufrufen einer benutzerdefinierten Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).  
  
 Funktionen können auch im Modell selbst deklariert werden. Im Modell deklarierte Funktionen werden auf die gleiche Weise ausgeführt wie Funktionen, die inline im Befehl deklariert wurden. Weitere Informationen finden Sie unter [benutzerdefinierte Funktionen](user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Entity SQL-Befehl definiert eine `Products` -Funktion, die die zurückgegebenen Produkte anhand eines ganzzahligen Werts filtert.  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Entity SQL-Befehl definiert eine `StringReturnsCollection` -Funktion, die anhand einer Auflistung von Zeichenfolgen die zurückgegebenen Kontakte filtert.  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Entity SQL Language (Entity SQL-Sprache)](entity-sql-language.md)
