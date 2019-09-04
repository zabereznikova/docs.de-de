---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 9495e5daf88326c5a682172d835c3349fe79e571
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248759"
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
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die PrimitiveType-Ergebnisse](../how-to-execute-a-query-that-returns-primitivetype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Siehe auch

- [Namespaces](namespaces-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
