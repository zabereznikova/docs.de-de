---
title: Benutzerdefinierte Funktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9e5ad1f6edb0e719733edd2518c5d62a7fc6bdf7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180971"
---
# <a name="user-defined-functions-entity-sql"></a>Benutzerdefinierte Funktionen (Entity SQL)

Entity SQL unterstützt das Aufrufen von benutzerdefinierten Funktionen in einer Abfrage. Sie können diese Funktionen Inline mit der Abfrage (siehe Gewusst [wie: Anzeigen einer benutzerdefinierten Funktion](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) oder als Teil des konzeptionellen Modells (siehe Gewusst [wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))) definieren. Funktionen des konzeptionellen Modells werden als Entity SQL Befehl im [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) -Element eines [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) -Elements im konzeptionellen Modell definiert.  
  
 Entity SQL ermöglicht Ihnen, Funktionen im Abfragebefehl selbst zu definieren. Der [Funktions](function-entity-sql.md) Operator definiert Inline Funktionen. Sie können mehrere Funktionen in einem einzelnen Befehl definieren. Diese Funktionen können den gleichen Funktionsnamen aufweisen, solange die Funktionssignaturen eindeutig sind. Weitere Informationen finden Sie unter [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Siehe auch

- [Funktionen](functions-entity-sql.md)
