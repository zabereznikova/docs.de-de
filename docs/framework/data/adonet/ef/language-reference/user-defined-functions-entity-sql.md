---
title: Benutzerdefinierte Funktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9ddafb18a10ff2313fd27eab453907054a35218a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248767"
---
# <a name="user-defined-functions-entity-sql"></a>Benutzerdefinierte Funktionen (Entity SQL)
Entity SQL unterstützt das Aufrufen von benutzerdefinierten Funktionen in einer Abfrage. Sie können diese Funktionen Inline mit der Abfrage definieren (weitere [Informationen finden Sie unter Vorgehensweise: Aufgerufen wird eine benutzerdefinierte Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) oder als Teil des konzeptionellen Modells (siehe [Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))Modell). Funktionen des konzeptionellen Modells werden als Entity SQL Befehl im [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) -Element eines [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) -Elements im konzeptionellen Modell definiert.  
  
 Entity SQL ermöglicht Ihnen, Funktionen im Abfragebefehl selbst zu definieren. Der [Funktions](function-entity-sql.md) Operator definiert Inline Funktionen. Sie können mehrere Funktionen in einem einzelnen Befehl definieren. Diese Funktionen können den gleichen Funktionsnamen aufweisen, solange die Funktionssignaturen eindeutig sind. Weitere Informationen finden Sie unter [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Siehe auch

- [Funktionen](functions-entity-sql.md)
