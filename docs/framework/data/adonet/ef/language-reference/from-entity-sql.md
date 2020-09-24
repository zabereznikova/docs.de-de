---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 8affac82fb1813aa0282540b5dc2f47d42234a1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148053"
---
# <a name="from-entity-sql"></a>FROM (Entity SQL)

Gibt die in [Select](select-entity-sql.md) -Anweisungen verwendete Auflistung an.

## <a name="syntax"></a>Syntax

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a>Argumente

`expression` \
Jeder gültige, eine Auflistung zurückgebende Abfrageausdruck, die als Quelle in einer `SELECT`-Anweisung verwendet werden kann.

## <a name="remarks"></a>Bemerkungen

Eine `FROM`-Klausel ist eine durch Kommas getrennte Liste von einem oder mehreren `FROM`-Klauselelementen. Die `FROM`-Klausel kann verwendet werden, um eine oder mehrere Quellen für eine `SELECT`-Anweisung anzugeben. Die einfachste Form einer `FROM`-Klausel ist ein einzelner, eine Auflistung und ein Alias festlegender Abfrageausdruck, der als Quelle in einer `SELECT`-Anweisung verwendet wird, wie im folgenden Beispiel veranschaulicht:

`FROM C as c`

## <a name="from-clause-items"></a>FROM-Klauselelemente

Jedes `FROM`-Klauselelement verweist auf eine Quellauflistung in der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfrage. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt die folgenden Klassen von `FROM`-Klauselelementen: einfache `FROM`-Klauselelemente, `JOIN FROM`-Klauselelemente und `APPLY FROM`-Klauselelemente. Jedes dieser `FROM`-Klauselelemente wird in den folgenden Abschnitten ausführlicher beschrieben.

### <a name="simple-from-clause-item"></a>Einfaches FROM-Klauselelement

Das einfachste `FROM`-Klauselelement ist ein einzelner Ausdruck, der eine Auflistung und einen Alias identifiziert. Bei dem Ausdruck kann es sich einfach um eine Entitätenmenge, eine Unterabfrage oder um einen anderen Ausdruck vom Auflistungstyp handeln. Hier ein Beispiel:

```sql
LOB.Customers as c
```

Die Aliasspezifikation ist optional. Eine alternative Spezifikation vom oben erwähnten FROM-Klauselelement finden Sie im Folgenden:

```sql
LOB.Customers
```

Wenn kein Alias angegeben wird, erzeugt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] auf der Grundlage des Auflistungsausdrucks einen Alias.

### <a name="join-from-clause-item"></a>JOIN FROM-Klauselelement

Ein `JOIN FROM`-Klauselelement stellt einen Join zwischen zwei `FROM`-Klauselelementen dar. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt Kreuzjoins, innere Joins, linke und rechte äußere Verknüpfungen und vollständige äußere Joins. Alle diese Joins werden ähnlich wie in Transact-SQL unterstützt. Wie bei Transact-SQL müssen die beiden Klauseln, die an beteiligt sind, `FROM` `JOIN` unabhängig sein. Sie können demnach nicht korreliert werden. Für diese Fälle kann `CROSS APPLY` oder `OUTER APPLY` verwendet werden.

#### <a name="cross-joins"></a>Cross Joins

Ein `CROSS JOIN`-Abfrageausdruck erzeugt das kartesische Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:

`FROM C AS c CROSS JOIN D as d`

#### <a name="inner-joins"></a>Inner Joins

`INNER JOIN` erzeugt ein eingeschränktes kartesisches Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:

`FROM C AS c [INNER] JOIN D AS d ON e`

Der vorige Abfrageausdruck verarbeitet eine Kombination aller Elemente der linken Auflistung gepaart mit jedem Element der rechten Auflistung, wenn die `ON`-Bedingung "true" ist. Wenn keine `ON`-Bedingung angegeben wird, degeneriert ein `INNER JOIN` zu einem `CROSS JOIN`.

#### <a name="left-outer-joins-and-right-outer-joins"></a>Linke äußere Verknüpfungen und rechte äußere Verknüpfungen

Ein `OUTER JOIN`-Abfrageausdruck erzeugt ein eingeschränktes kartesisches Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:

`FROM C AS c LEFT OUTER JOIN D AS d ON e`

Der vorige Abfrageausdruck verarbeitet eine Kombination aller Elemente der linken Auflistung gepaart mit jedem Element der rechten Auflistung, wenn die `ON`-Bedingung "true" ist. Wenn die `ON`-Bedingung "false" ist, verarbeitet der Ausdruck eine einzelne Instanz des linken Elements gepaart mit dem rechten Element mit dem Wert Null.

Ein `RIGHT OUTER JOIN` kann auf eine ähnliche Weise ausgedrückt werden.

#### <a name="full-outer-joins"></a>Full Outer Joins

Ein expliziter `FULL OUTER JOIN` erzeugt ein eingeschränktes kartesisches Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:

`FROM C AS c FULL OUTER JOIN D AS d ON e`

Der vorige Abfrageausdruck verarbeitet eine Kombination aller Elemente der linken Auflistung gepaart mit jedem Element der rechten Auflistung, wenn die `ON`-Bedingung "true" ist. Wenn die `ON`-Bedingung "false" ist, verarbeitet der Ausdruck eine Instanz des linken Elements gepaart mit dem rechten Element mit dem Wert NULL. Außerdem wird eine Instanz des rechten Elements gepaart mit dem linken Element mit dem Wert NULL verarbeitet.

> [!NOTE]
> Um die Kompatibilität mit SQL-92 beizubehalten, ist das äußerste Schlüsselwort in Transact-SQL optional. `LEFT JOIN`, `RIGHT JOIN` und `FULL JOIN` sind daher Synonyme für `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` und `FULL OUTER JOIN`.

### <a name="apply-clause-item"></a>APPLY-Klauselelement

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Arten von `APPLY`: `CROSS APPLY` und `OUTER APPLY`.

Ein `CROSS APPLY` erzeugt eine eindeutige Kombination aller Elemente der linken Auflistung mit einem Element der rechten Auflistung, indem der rechte Ausdruck ausgewertet wird. Mit `CROSS APPLY` ist der rechte Ausdruck funktional abhängig vom linken Element, wie das folgende Beispiel für eine zugeordnete Auflistung veranschaulicht:

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

Das Verhalten von `CROSS APPLY` ähnelt der Verknüpfungsliste. Wenn der rechte Ausdruck als leere Auflistung ausgewertet wird, erzeugt `CROSS APPLY` für diese Instanz des linken Elements keine Paarungen.

`OUTER APPLY` ähnelt `CROSS APPLY`, abgesehen davon, dass eine Paarung auch dann erzeugt wird, wenn der rechte Ausdruck als leere Auflistung ausgewertet wird. Im Folgenden finden Sie ein Beispiel für ein `OUTER APPLY`.

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> Anders als bei Transact-SQL ist ein expliziter unnest-Schritt in nicht erforderlich [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .

> [!NOTE]
> `CROSS` die `OUTER APPLY` Operatoren und wurden in SQL Server 2005 eingeführt. In einigen Fällen kann die Abfragepipeline Transact-SQL erzeugen, die `CROSS APPLY`- und/oder `OUTER APPLY`-Operatoren enthält. Da einige Back-End-Anbieter, einschließlich Versionen von SQL Server vor SQL Server 2005, diese Operatoren nicht unterstützen, können solche Abfragen auf diesen Back-End-Anbietern nicht ausgeführt werden.
>
> Typische Szenarios, in denen `CROSS APPLY`- und/oder `OUTER APPLY`-Operatoren in der Ausgabeabfrage vorhanden sein können, sind beispielsweise korrelierte Unterabfragen mit Paging, AnyElement über einer korrelierten Unterabfrage oder über einer durch Navigation erzeugten Auflistung, LINQ-Abfragen, die Elementselektoren akzeptierende Gruppierungsmethoden verwenden, Abfragen, für die ein `CROSS APPLY` oder ein `OUTER APPLY` explizit angegeben wurden oder Abfragen, die ein `DEREF`-Konstrukt über einem `REF`-Konstrukt enthalten.

## <a name="multiple-collections-in-the-from-clause"></a>Mehrere Auflistungen in der FROM-Klausel

Die `FROM`-Klausel kann mehrere durch Kommas getrennte Auflistungen enthalten. In diesem Fall wird davon ausgegangen, dass die Auflistungen verknüpft sind. Dies ist vergleichbar mit einem n-fachen CROSS JOIN.

Im folgenden Beispiel `C` sind und unabhängige Auflistungen `D` , ist jedoch von `c.Names` abhängig `C` .

```sql
FROM C AS c, D AS d, c.Names AS e
```

Das vorherige Beispiel ist mit dem folgenden Beispiel logisch äquivalent:

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a>Linke Korrelation

 Elemente in der `FROM`-Klausel können auf in früheren Klauseln angegebene Elemente verweisen. Im folgenden Beispiel sind `C` und `D` unabhängige Auflistungen, `c.Names` ist jedoch von `C` abhängig:

```sql
from C as c, D as d, c.Names as e
```

Dies ist logisch äquivalent zu:

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a>Semantik

Es wird logisch davon ausgegangen, dass die Auflistungen in der `FROM`-Klausel zu einem `n`-fachen Cross Join gehören (außer im Fall eines einfachen Cross Join). Aliase werden in der `FROM`-Klausel von links nach rechts verarbeitet und dem aktuellen Gültigkeitsbereich hinzugefügt, um später auf sie verweisen zu können. Es wird angenommen, dass die `FROM`-Klausel ein Zeilenmultiset erzeugt. Für jedes Objekt in der `FROM`-Klausel ist ein Feld vorhanden, dass ein einzelnes Element dieser Auflistung darstellt.

Die `FROM`-Klausel erzeugt logisch eine Zeilenmultimenge vom Row(c, d, e)-Typ. Es wird angenommen, dass die Felder c, d und e den Elementtyp `C`, `D` und `c.Names` aufweisen.

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] führt einen Alias für jedes einfache `FROM`-Klauselelement im Bereich ein. Im folgenden FROM-Klauselausschnitt sind die im Bereich eingeführten Namen beispielsweise c, d und e.

```sql
from (C as c join D as d) cross apply c.Names as e
```

In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (im Gegensatz zu Transact-SQL) `FROM` führt die-Klausel nur die Aliase in den Gültigkeitsbereich ein. Alle Verweise auf Spalten (Eigenschaften) dieser Auflistungen müssen mit dem Alias qualifiziert werden.

## <a name="pulling-up-keys-from-nested-queries"></a>Ausführen von Pull-Vorgängen für Schlüssel aus geschachtelten Abfragen

Bestimmte Typen von Abfragen, die die Ausführung von Pull-Vorgängen für Schlüssel aus einer geschachtelten Abfrage erfordern, werden nicht unterstützt. Beispielsweise ist die folgende Abfrage gültig:

```sql
select c.Orders from Customers as c
```

Die folgende Abfrage ist jedoch ungültig, da die geschachtelte Abfrage nicht über Schlüssel verfügt:

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Abfrageausdrücke](query-expressions-entity-sql.md)
- [Strukturierte Typen, die NULL-Werte zulassen](nullable-structured-types-entity-sql.md)
