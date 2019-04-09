---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 44b28ec265a18632e936ba05e25840a03f68da90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119014"
---
# <a name="limit-entity-sql"></a>LIMIT (Entity SQL)
Das physische Paging kann mit LIMIT-Unterklauseln in der ORDER BY-Klausel durchgeführt werden. LIMIT kann nicht ohne ORDER BY-Klausel verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a>Argumente  
 `n`  
 Die Anzahl der auszuwählenden Elemente.  
  
 Wenn eine ORDER BY-Klausel den Ausdruck LIMIT als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den LIMIT-Ausdruck begrenzt. LIMIT 5 z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen. Die Funktionsweise von LIMIT entspricht der von TOP, mit dem Unterschied, dass LIMIT nur mit einer ORDER BY-Klausel verwendet werden kann. SKIP und LIMIT können zusammen mit einer ORDER BY-Klausel voneinander unabhängig verwendet werden.  
  
> [!NOTE]
>  Eine Entity Sql-Abfrage gilt als ungültig, wenn im selben Abfrageausdruck ein TOP-Modifizierer und eine SKIP-Unterklausel vorhanden sind. Die Abfrage sollte umgeschrieben werden, indem der TOP-Ausdruck in einen LIMIT-Ausdruck geändert wird.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der ORDER BY-Operator mit LIMIT verwendet, um für die von der SELECT-Anweisung zurückgegebenen Objekte die zu verwendende Sortierreihenfolge anzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>Siehe auch

- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Vorgehensweise: Seitenweise Abfrageresultate durch Navigieren](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
