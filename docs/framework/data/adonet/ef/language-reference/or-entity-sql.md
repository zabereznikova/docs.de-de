---
title: '|| (OR) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ba0c376bc0b57013fe4701a1f9e84fdd9a5ed62a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Verknüpft zwei `Boolean` -Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argumente  
 `boolean_expression`  
 Jeder gültige Ausdruck, der ein `Boolean`zurückgibt.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` , wenn eine der Bedingungen `true`ist; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 OR ist ein logischer Operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Er wird zur Verknüpfung zweier Bedingungen verwendet. Wenn in einer Anweisung mehrere logische Operatoren verwendet werden, werden OR-Operatoren nach AND-Operatoren ausgewertet. Sie können jedoch die Reihenfolge der Auswertung ändern, indem Sie Klammern verwenden.  
  
 Zwei senkrechte Striche (&#124; &#124;) haben dieselbe Funktion wie der OR-Operator.  
  
 In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|true|true|  
|`FALSE`|true|false|NULL|  
|`NULL`|true|NULL|NULL|  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den OR-Operator, um zwei `Boolean` -Ausdrücke zu verknüpfen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
