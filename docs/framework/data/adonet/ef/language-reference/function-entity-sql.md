---
title: "FUNCTION (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# FUNCTION (Entity SQL)
Definiert eine Funktion im Bereich eines Entity SQL\-Abfragebefehls.  
  
## Syntax  
  
```  
  
FUNCTION function-name( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition>)   
                | REF (data_type)   
                | ROW (row_expression)   
        }   
```  
  
## Argumente  
 `function-name`  
 Der Name der Funktion.  
  
 `parameter-name`  
 Der Name eines Parameters in der Funktion.  
  
 `function_expression`  
 Ein gültiger Entity SQL\-Ausdruck, der die Funktion darstellt. Der Befehl in der Funktion kann auf `parameter_name`\-Parameter, die an die Funktion übergeben wurden, angewendet werden.  
  
 `data_type`  
 Der Name eines unterstützten Typs.  
  
 COLLECTION \( \<type\_definition`>` \)  
 Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.  
  
 REF **\(** `data_type` **\)**  
 Ein Ausdruck, der einen Verweis auf einen Entitätstyp zurückgibt.  
  
 ROW **\(** `row_expression` **\)**  
 Ein Ausdruck, der anonyme strukturell eingegebene Datensätze von mindestens einem Wert zurückgibt. Weitere Informationen finden Sie unter [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## Hinweise  
 Mehrere Funktionen mit dem gleichen Namen können inline deklariert werden, sofern sie unterschiedliche Funktionssignaturen aufweisen. Weitere Informationen finden Sie unter [Auflösung von Funktionsüberladungen](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
 Eine Inlinefunktion kann nur in einem Entity SQL\-Befehl aufgerufen werden, nachdem sie in diesem Befehl definiert wurde. Eine Inlinefunktion kann jedoch in einer anderen Inlinefunktion aufgerufen werden, bevor oder nachdem die aufgerufene Funktion definiert wurde. Im folgenden Beispiel wird Funktion B von Funktion A aufgerufen, bevor Funktion B definiert wird:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Aufrufen einer benutzerdefinierten Funktion](http://msdn.microsoft.com/de-de/ad131b86-8b4e-4747-8605-d4fc64fb9d02).  
  
 Funktionen können auch im Modell selbst deklariert werden. Im Modell deklarierte Funktionen werden auf die gleiche Weise ausgeführt wie Funktionen, die inline im Befehl deklariert wurden. Weitere Informationen finden Sie unter [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
## Beispiel  
 Der folgende Entity SQL\-Befehl definiert eine `Products`\-Funktion, die die zurückgegebenen Produkte anhand eines ganzzahligen Werts filtert.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## Beispiel  
 Der folgende Entity SQL\-Befehl definiert eine `StringReturnsCollection`\-Funktion, die anhand einer Auflistung von Zeichenfolgen die zurückgegebenen Kontakte filtert.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Entity SQL\-Sprache](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)