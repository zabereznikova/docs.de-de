---
title: Benutzerdefinierte Funktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: a3c9cda162e77517d480d9e48eb80fa62dd1c161
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="user-defined-functions-entity-sql"></a>Benutzerdefinierte Funktionen (Entity SQL)
Entity SQL unterstützt das Aufrufen von benutzerdefinierten Funktionen in einer Abfrage. Sie können diese Funktionen Inline mit der Abfrage definieren (finden Sie unter [wie: Aufrufen einer benutzerdefinierten Funktion](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) oder als Teil des konzeptionellen Modells (finden Sie unter [wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)). Konzeptionelle Modellfunktionen werden als Entity SQL-Befehl in definiert die [DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) Element von einem [Funktion](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) Element im konzeptionellen Modell.  
  
 Entity SQL ermöglicht Ihnen, Funktionen im Abfragebefehl selbst zu definieren. Die [Funktion](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) -Operator definiert Inlinefunktionen. Sie können mehrere Funktionen in einem einzelnen Befehl definieren. Diese Funktionen können den gleichen Funktionsnamen aufweisen, solange die Funktionssignaturen eindeutig sind. Weitere Informationen finden Sie unter [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
