---
title: Konstruktionstypen (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 48dab533e26d6353c29667d81ea547f4b15d280f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="constructing-types-entity-sql"></a>Konstruktionstypen (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]stellt drei Arten von Konstruktoren bereit: Zeilenkonstruktoren, Konstruktoren benannter Typen und Auflistungskonstruktoren.  
  
## <a name="row-constructors"></a>Zeilenkonstruktoren  
 Zeilenkonstruktoren werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zur Erstellung anonymer, strukturell typisierter Datensätze aus einem oder mehreren Werten verwendet. Beim Ergebnistyp eines Zeilenkonstruktors handelt es sich um einen Zeilentyp, dessen Feldtypen den Typen der zur Erstellung der Zeile verwendeten Werten entsprechen. Der folgende Ausdruck erstellt z. B. einen Wert vom Typ `Record(a int, b string, c int)`:  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 Wenn für einen Ausdruck in einem Zeilenkonstruktor kein Alias angegeben ist, wird vom Entity Framework ein Alias generiert. Weitere Informationen finden Sie im Abschnitt "Regeln für das Aliasing" im [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Die folgenden Regeln gelten für Ausdrucksaliasing in einem Zeilenkonstruktor:  
  
-   Ausdrücke in einem Zeilenkonstruktor können nicht auf andere Aliase im gleichen Konstruktor verweisen.  
  
-   Zwei Ausdrücke im gleichen Zeilenkonstruktor können nicht über den gleichen Alias verfügen.  
  
 Weitere Informationen zu Zeilenkonstruktoren, finden Sie unter [Zeile](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="collection-constructors"></a>Auflistungskonstruktoren  
 Mithilfe von Auflistungskonstruktoren wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] aus einer Liste mit Werten eine Instanz eines Multisets erstellt. Alle Werte im Konstruktor müssen vom beiderseitig kompatiblen Typ `T` sein, und der Konstruktor erstellt eine Auflistung des Typs `Multiset<T>`. Zum Beispiel erstellt der folgende Ausdruck eine Auflistung von ganzen Zahlen:  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 Leere Multiset-Konstruktoren sind nicht zugelassen, da der Typ der Elemente nicht bestimmt werden kann. Der folgende Ausdruck ist ungültig:  
  
 `multiset() {}`  
  
 Weitere Informationen finden Sie unter [MULTIMENGE](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).  
  
## <a name="named-type-constructors-namedtype-initializers"></a>Konstruktoren benannter Typen (NamedType-Initialisierer)  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ermöglicht Typenkonstruktoren (Initialisierern) das Erstellen von Instanzen benannter komplexer Typen und Entitätstypen. Der folgende Ausdruck erstellt z. B. eine Instanz eines `Person`-Typs.  
  
 `Person("abc", 12)`  
  
 Mit dem folgenden Ausdruck wird eine Instanz eines komplexen Typs erstellt.  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 Mit dem folgenden Ausdruck wird eine Instanz eines geschachtelten komplexen Typs erstellt.  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 Mit dem folgenden Ausdruck wird eine Instanz einer Entität mit einem geschachtelten komplexen Typ erstellt.  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 Im folgenden Beispiel wird gezeigt, wie eine Eigenschaft eines komplexen Typs mit NULL initialisiert wird. `MyModel.ZipCode(‘98118’, null)`  
  
 Die Reihenfolge der Argumente des Konstruktors sollten mit der Reihenfolge der Deklaration der Attribute des Typs übereinstimmen.  
  
 Weitere Informationen finden Sie unter [Typkonstruktor mit dem Namen](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)
