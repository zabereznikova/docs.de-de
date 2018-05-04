---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 3b63ca6ade93331b9d1c3ef3e8de15ed520864dc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)
Physisches Paging kann mithilfe der SKIP-Unterklausel in der ORDER BY-Klausel durchgeführt werden. SKIP kann nicht ohne die ORDER BY-Klausel verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>Argumente  
 `n`  
 Die Anzahl zu überspringender Elemente.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen. Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben.  
  
> [!NOTE]
>  Eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage ist ungültig, wenn im selben Abfrageausdruck sowohl ein TOP-Modifizierer als auch eine SKIP-Unterklausel vorhanden sind. In der Abfrage sollte der TOP-Ausdruck in einen LIMIT-Ausdruck geändert werden.  
  
> [!NOTE]
>  Die Verwendung von SKIP mit ORDER BY für Nichtschlüsselspalten kann in [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]zu falschen Ergebnissen führen. Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält. Der Grund dafür ist die Übersetzung von SKIP für [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]. Im folgenden Code können beispielsweise mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` Werte doppelt enthält:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 In der  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage in [diesem](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) Beispiel wird der ORDER BY-Operator mit SKIP verwendet, um für die von der SELECT-Anweisung zurückgegebenen Objekte die zu verwendende Sortierreihenfolge anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Vorgehensweise: seitenweise durch Abfrageresultate navigieren](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
