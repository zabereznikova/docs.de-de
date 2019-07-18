---
title: Konstruktionstypen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: d43793b1d514b9dd81f524a30cd5bf1622aa5258
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64632223"
---
# <a name="constructing-types-entity-sql"></a>Konstruktionstypen (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt drei Arten von Konstruktoren bereit: Zeilenkonstruktoren, Konstruktoren benannter Typen und Auflistungskonstruktoren.  
  
## <a name="row-constructors"></a>Zeilenkonstruktoren  
 Zeilenkonstruktoren werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zur Erstellung anonymer, strukturell typisierter Datensätze aus einem oder mehreren Werten verwendet. Beim Ergebnistyp eines Zeilenkonstruktors handelt es sich um einen Zeilentyp, dessen Feldtypen den Typen der zur Erstellung der Zeile verwendeten Werten entsprechen. Der folgende Ausdruck erstellt z. B. einen Wert vom Typ `Record(a int, b string, c int)`:  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 Wenn für einen Ausdruck in einem Zeilenkonstruktor kein Alias angegeben ist, wird vom Entity Framework ein Alias generiert. Weitere Informationen finden Sie im Abschnitt "Regeln für das Aliasing" im [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Die folgenden Regeln gelten für Ausdrucksaliasing in einem Zeilenkonstruktor:  
  
- Ausdrücke in einem Zeilenkonstruktor können nicht auf andere Aliase im gleichen Konstruktor verweisen.  
  
- Zwei Ausdrücke im gleichen Zeilenkonstruktor können nicht über den gleichen Alias verfügen.  
  
 Weitere Informationen zu Zeilenkonstruktoren finden Sie unter [Zeile](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
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
  
 Weitere Informationen finden Sie unter [mit dem Namen der Typkonstruktor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)
