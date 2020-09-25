---
title: Paging (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 42f685e0b84109f3099b501b2a75e681af1ea1bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177474"
---
# <a name="paging-entity-sql"></a>Paging (Entity SQL)

Das physische Paging kann mithilfe der [Skip](skip-entity-sql.md) -und [Limit](limit-entity-sql.md) -Unterklauseln in der [Order by](order-by-entity-sql.md) -Klausel durchgeführt werden. Um physisches Paging deterministisch durchzuführen, sollten Sie SKIP und LIMIT verwenden. Wenn Sie nur die Anzahl der Zeilen im Ergebnis auf nicht deterministische Weise einschränken möchten, sollten Sie [Top](top-entity-sql.md)verwenden. TOP und SKIP/LIMIT schließen sich gegenseitig aus.  
  
## <a name="top-overview"></a>Übersicht über 'TOP'  

 Der SELECT-Klausel kann hinter dem optionalen ALL/DISTINCT-Modifizierer eine TOP-Unterklausel angefügt werden. Die TOP-Unterklausel gibt an, dass nur der erste Zeilensatz aus dem Abfrageergebnis zurückgegeben wird. Weitere Informationen finden Sie unter [Top](top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Übersicht über 'SKIP' und 'LIMIT'  

 SKIP und LIMIT sind Teil der ORDER BY-Klausel. Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen. Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben. Wenn eine ORDER BY-Klausel den Ausdruck LIMIT als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den LIMIT-Ausdruck begrenzt. LIMIT 5 z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen. SKIP und LIMIT müssen nicht gemeinsam verwendet werden; Sie können auch nur SKIP oder nur LIMIT mit der ORDER BY-Klausel verwenden. Weitere Informationen finden Sie unter den folgenden Themen:  
  
- [SKIP](skip-entity-sql.md)  
  
- [Ans](limit-entity-sql.md)  
  
- [ORDER BY](order-by-entity-sql.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Gewusst wie: Seitenweise durch Abfrageresultate navigieren](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
