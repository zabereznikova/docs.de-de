---
title: Paging (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6188587a8b588128092f5d9f02f6962159b928e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="paging-entity-sql"></a>Paging (Entity SQL)
Physisches Paging kann ausgeführt werden, mithilfe der [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) und [Grenzwert](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) -Unterklausel in der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) Klausel. Um physisches Paging deterministisch durchzuführen, sollten Sie SKIP und LIMIT verwenden. Wenn Sie nur die Anzahl der Zeilen in einer Tabelle in einer nicht-deterministische Weise beschränken möchten, verwenden Sie [oben](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). 
          TOP und SKIP/LIMIT schließen sich gegenseitig aus.  
  
## <a name="top-overview"></a>Übersicht über 'TOP'  
 Der SELECT-Klausel kann hinter dem optionalen ALL/DISTINCT-Modifizierer eine TOP-Unterklausel angefügt werden. Die TOP-Unterklausel gibt an, dass nur der erste Zeilensatz aus dem Abfrageergebnis zurückgegeben wird. Weitere Informationen finden Sie unter [oben](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Übersicht über 'SKIP' und 'LIMIT'  
 SKIP und LIMIT sind Teil der ORDER BY-Klausel. Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen. Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben. Wenn eine ORDER BY-Klausel den Ausdruck LIMIT als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den LIMIT-Ausdruck begrenzt. 
          LIMIT 5 z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen. 
          SKIP und LIMIT müssen nicht gemeinsam verwendet werden; Sie können auch nur SKIP oder nur LIMIT mit der ORDER BY-Klausel verwenden. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [ÜBERSPRINGEN](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [GRENZWERT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Vorgehensweise: seitenweise durch Abfrageresultate navigieren](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)
