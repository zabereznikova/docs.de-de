---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297862"
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
  
1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Siehe auch

- [Namespaces](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
