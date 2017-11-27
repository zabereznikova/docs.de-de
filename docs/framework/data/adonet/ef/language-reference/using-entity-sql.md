---
title: USING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c506484908d6b0ffe3a11e33b51d0bcc2d27c25c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-entity-sql"></a>USING (Entity SQL)
Legt in einem Abfrageausdruck verwendete Namespaces fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argumente  
 `alias`  
 Legt einen kürzeren Alias für die Qualifizierung eines Namespace fest.  
  
 `namespace`  
 Jeder gültige Namespace.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage legt mithilfe des USING-Operators Namespaces fest, die in einem Abfrageausdruck verwendet werden. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Namespaces](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
