---
title: Übersetzen von Standardabfrageoperatoren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: af22b6a895fef8037eb5c069ffb7cb23d1333531
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833679"
---
# <a name="standard-query-operator-translation"></a>Übersetzen von Standardabfrageoperatoren

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt Standard Abfrage Operatoren in SQL-Befehle. Der Abfrage Prozessor der Datenbank bestimmt die Ausführungs Semantik der SQL-Übersetzung.

Standard Abfrage Operatoren werden für *Sequenzen*definiert. Eine Sequenz wird *geordnet* und basiert auf der Verweis Identität für jedes Element der Sequenz. Weitere Informationen finden Sie unter [Übersicht über Standard Abfrage Operatoren (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) oder unter [Übersicht über Standard Abfrage Operatoren (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

SQL behandelt hauptsächlich *ungeordnete Sätze von Werten*. Die Sortierung ist in der Regel ein explizit angegebener, nachgelagerter Prozess, der auf das Endergebnis einer Abfrage und nicht auf Zwischenergebnisse angewendet wird. Die Identität wird durch Werte definiert. Aus diesem Grund werden SQL-Abfragen für die Handhabung von Multisets (*Taschen*) anstelle von *Sätzen*verstanden.

Die folgenden Abschnitte beschreiben die Unterschiede zwischen den Standardabfrageoperatoren und ihrer SQL-Übersetzung für den SQL Server-Anbieter in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

## <a name="operator-support"></a>Operatorunterstützung

### <a name="concat"></a>Concat

Die <xref:System.Linq.Enumerable.Concat%2A>-Methode ist für geordnete Multisets definiert, bei denen die Reihenfolge des Empfängers und des Arguments identisch ist. <xref:System.Linq.Enumerable.Concat%2A> funktioniert als `UNION ALL` über die Multisets, gefolgt von der allgemeinen Reihenfolge.

Die Sortierung in SQL ist der letzte Schritt vor dem Erzeugen von Ergebnissen. <xref:System.Linq.Enumerable.Concat%2A> behält die Reihenfolge der Argumente nicht bei. Um die entsprechende Sortierung sicherzustellen, müssen Sie die Ergebnisse von <xref:System.Linq.Enumerable.Concat%2A> explizit sortieren.

### <a name="intersect-except-union"></a>Intersect, Except, Union

Die <xref:System.Linq.Enumerable.Intersect%2A>-Methode und die <xref:System.Linq.Enumerable.Except%2A>-Methode sind nur für Sätze gut definiert. Die Semantik für Multisets ist nicht definiert.

Die <xref:System.Linq.Enumerable.Union%2A>-Methode ist für Multisets definiert, und zwar als unsortierte Verkettung der Multisets (effektiv als Ergebnis der UNION ALL-Klausel in SQL).

### <a name="take-skip"></a>Take, Skip

<xref:System.Linq.Enumerable.Take%2A>-und <xref:System.Linq.Enumerable.Skip%2A>-Methoden sind nur für *geordnete Sätze*gut definiert. Die Semantik für ungeordnete Sätze oder Multisets ist nicht definiert.

> [!NOTE]
> <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> haben bestimmte Einschränkungen, wenn Sie in Abfragen für SQL Server 2000 verwendet werden. Weitere Informationen finden Sie im Eintrag "überspringen und Entfernen von Ausnahmen in SQL Server 2000" in der [Problem](troubleshooting.md)Behandlung.

Aufgrund von Einschränkungen bei der Reihenfolge in SQL versucht [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], die Reihenfolge des Arguments dieser Methoden auf das Ergebnis der-Methode zu verschieben. Betrachten Sie z. B. die folgende [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage:

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

Das generierte SQL für diesen Code verschiebt die Sortierung wie folgt ans Ende:

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

Es ist offensichtlich, dass die angegebene Sortierung konsistent sein muss, wenn <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> verkettet werden. Andernfalls sind die Ergebnisse nicht definiert.

<xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> sind für nicht negative, konstante Integralargumente auf der Basis der Spezifikation für Standardabfrageoperatoren gut definiert.

### <a name="operators-with-no-translation"></a>Operatoren ohne Übersetzung

Die folgenden Methoden werden nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt. Der einfachste Grund ist der Unterschied zwischen ungeordneten Multisets und Sequenzen.

|Operatoren|Begründung|
|---------------|---------------|
|<xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>|SQL-Abfragen verwenden Multisets, keine Sequenzen. `ORDER BY` muss die letzte Klausel sein, die auf die Ergebnisse angewendet wird. Aus diesem Grund gibt es keine allgemeine Übersetzung dieser beiden Methoden.|
|<xref:System.Linq.Enumerable.Reverse%2A>|Die Übersetzung dieser Methode ist für eine geordnete Menge möglich. Sie wird jedoch derzeit von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht übersetzt.|
|<xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A>|Die Übersetzung dieser Methoden ist für eine geordnete Menge möglich. Sie werden jedoch derzeit von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht übersetzt.|
|<xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|SQL-Abfragen verwenden Multisets, keine indizierbaren Sequenzen.|
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (Überladung mit Standard-Arg)|Im Allgemeinen kann ein Standardwert nicht für ein beliebiges Tupel angegeben werden. NULL-Werte für Tupel sind in einigen Fällen durch äußere Joins möglich.|

## <a name="expression-translation"></a>Ausdrucksübersetzung

### <a name="null-semantics"></a>NULL-Semantik

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gibt keine NULL-Vergleichs Semantik für SQL an. Vergleichsoperatoren werden syntaktisch zu ihren SQL-Entsprechungen übersetzt. Aus diesem Grund reflektiert die Semantik SQL-Semantik, die von Server- oder Verbindungseinstellungen definiert wird. Beispielsweise werden zwei NULL-Werte unter den Standard SQL Server Einstellungen als ungleich betrachtet, Sie können jedoch die Einstellungen ändern, um die Semantik zu ändern. in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] werden Servereinstellungen beim Übersetzen von Abfragen nicht berücksichtigt.

Ein Vergleich mit dem NULL-Literal wird in die entsprechende SQL-Version (`is null` oder `is not null`) übersetzt.

Der Wert von `null` in der Zusammenstellung wird von SQL-Server definiert. die Sortierung wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht geändert.

### <a name="aggregates"></a>Aggregate

Die Aggregationsmethode für Standardabfrageoperatoren <xref:System.Linq.Enumerable.Sum%2A> ergibt bei einer leeren Sequenz oder bei einer aus Nullen bestehenden Sequenz 0. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]bleibt die Semantik von SQL unverändert, und <xref:System.Linq.Enumerable.Sum%2A> ergibt eine `null` anstelle von NULL für eine leere Sequenz oder eine Sequenz, die nur Nullen enthält.

SQL-Einschränkungen für Zwischenergebnisse gelten in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für Summen. Die <xref:System.Linq.Enumerable.Sum%2A> von 32-Bit-Ganzzahlmengen wird nicht berechnet, indem man 64-Bit-Ergebnisse verwendet. Bei einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Übersetzung von <xref:System.Linq.Enumerable.Sum%2A> kann es zu einem Überlauf kommen, auch wenn die Implementierung von Standardabfrageoperatoren bei der entsprechenden Sequenz im Arbeitsspeicher keinen Überlauf verursacht.

In gleicher Weise wird die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Übersetzung von <xref:System.Linq.Enumerable.Average%2A> zu Ganzzahlen als `integer` und nicht als `double` übersetzt.

### <a name="entity-arguments"></a>Entitätsargumente

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ermöglicht die Verwendung von Entitäts Typen in den Methoden <xref:System.Linq.Enumerable.GroupBy%2A> und <xref:System.Linq.Enumerable.OrderBy%2A>. In der Übersetzung dieser Operatoren gilt die Verwendung eines Arguments als Entsprechung zur Angabe aller Member dieses Typs. Der folgende Code ist z. B. äquivalent:

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a>Gleichwertige/vergleichbare Argumente

Die Gleichheit von Argumenten ist in der Implementierung der folgenden Methoden erforderlich:

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt Gleichheit und Vergleich für *flache* Argumente, jedoch nicht für Argumente, die Sequenzen sind oder enthalten. Ein flaches Argument ist ein Typ, der einer SQL-Zeile zugeordnet werden kann. Eine Projektion von einem oder mehreren statisch festgelegten Entitätstypen ohne Sequenz gilt als flaches Argument.

Im folgenden finden Sie Beispiele für flatarguments:

[!code-csharp[DLinqSQOTranslation#3](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

Im folgenden finden Sie Beispiele für nicht flache (hierarchische) Argumente:

[!code-csharp[DLinqSQOTranslation#4](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a>Visual Basic-Funktionsübersetzung

Die folgenden, vom Visual Basic-Compiler verwendeten Hilfsfunktionen werden in entsprechende SQL-Operatoren und -Funktionen übersetzt:

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

Konvertierungsmethoden:

|||||
|-|-|-|-|
|ToBoolean|ToSByte|ToByte|ToChar|
|ToCharArrayRankOne|ToDate|ToDecimal|ToDouble|
|ToInteger|ToUInteger|ToLong|ToULong|
|ToShort|ToUShort|ToSingle|ToString|

## <a name="inheritance-support"></a>Unterstützung von Vererbung

### <a name="inheritance-mapping-restrictions"></a>Einschränkungen der Vererbungszuordnung

Weitere Informationen finden Sie unter Vorgehens [Weise: Zuordnen von Vererbungs Hierarchien](how-to-map-inheritance-hierarchies.md).

### <a name="inheritance-in-queries"></a>Vererbung in Abfragen

C#-Umwandlungen werden nur in Projektionen unterstützt. An anderer Stelle verwendete Umwandlungen werden nicht übersetzt, sonder ignoriert. Neben den SQL-Funktionsnamen führt SQL tatsächlich nur das Äquivalent von Common Language Runtime (CLR) <xref:System.Convert> aus. Das heißt, SQL kann den Wert eines Typs ändern. Es gibt keine Entsprechung zu CLR-Umwandlungen, da es kein Konzept für die Neuinterpretation der gleichen Bits als die eines anderen Typs gibt. Aus diesem Grund funktioniert eine C#-Umwandlung nur lokal. Eine Remoteausführung ist nicht möglich.

Der `is`-Operator und der `as`-Operator sowie die `GetType`-Methode werden nicht auf den `Select`-Operator beschränkt. Sie können auch in anderen Abfrageoperatoren verwendet werden.

## <a name="sql-server-2008-support"></a>SQL Server 2008-Unterstützung

Ab .NET Framework 3.5 SP1 unterstützt LINQ to SQL das Mapping zu den in SQL Server 2008 neu eingeführten Datums- und Uhrzeittypen. Einschränkungen bestehen jedoch für die LINQ to SQL-Abfrageoperatoren, die beim Arbeiten mit den diesen neuen Typen zugeordneten Werten verwendet werden können.

### <a name="unsupported-query-operators"></a>Nicht unterstützte Abfrageoperatoren

Die folgenden Abfrageoperatoren werden nicht für Werte unterstützt, die den neuen Datums- und Uhrzeittypen von SQL Server zugeordnet sind: `DATETIME2`, `DATE`, `TIME` und `DATETIMEOFFSET`.

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

Weitere Informationen über das Mapping zu diesen SQL Server Datums-und Uhrzeit Typen finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md).

## <a name="sql-server-2005-support"></a>SQL Server 2005-Unterstützung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet keine Unterstützung für die folgenden SQL Server 2005-Features:

- Gespeicherte Prozeduren für SQL CLR.

- Benutzerdefinierter Typ.

- XML-Abfragefunktionen.

## <a name="sql-server-2000-support"></a>SQL Server 2000-Unterstützung

Die folgenden SQL Server Einschränkungen für 2000 (im Vergleich zu Microsoft SQL Server 2005) wirken sich auf die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Unterstützung aus.

### <a name="cross-apply-and-outer-apply-operators"></a>Cross Apply-Operator und Outer Apply-Operator

Diese Operatoren sind in SQL Server 2000 nicht verfügbar. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] versucht eine Reihe von erneuten Schreibvorgängen, um Sie durch geeignete Joins zu ersetzen.

`Cross Apply` und `Outer Apply` werden für Beziehungs Navigation generiert. Der Satz von Abfragen, für den solche erneuten Schreibzugriffe möglich sind, ist nicht klar definiert. Aus diesem Grund ist der minimale Satz von Abfragen, der für SQL Server 2000 unterstützt wird, der Satz, der keine Beziehungs Navigation umfasst.

### <a name="text--ntext"></a>text / ntext

Datentypen `text` / `ntext` können nicht in bestimmten Abfrage Vorgängen für `varchar(max)` / `nvarchar(max)`verwendet werden, die von Microsoft SQL Server 2005 unterstützt werden.

Für diese Einschränkung ist keine Lösung verfügbar. Sie können insbesondere `Distinct()` nicht für Ergebnisse verwenden, die Member enthalten, die der `text`-Spalte oder der `ntext`-Spalte zugeordnet sind.

### <a name="behavior-triggered-by-nested-queries"></a>Von verschachtelten Abfragen ausgelöstes Verhalten

SQL Server 2000-Binder (über SP4) verfügt über einige idiosyncraasen, die durch geschachtelte Queries ausgelöst werden. Der Satz von SQL-Abfragen, der diese Eigenheiten auslöst, ist nicht klar definiert. Aus diesem Grund können Sie nicht den Satz von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen definieren, die SQL Server Ausnahmen verursachen können.

### <a name="skip-and-take-operators"></a>Skip-Operator und Take-Operator

<xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> haben bestimmte Einschränkungen, wenn Sie in Abfragen für SQL Server 2000 verwendet werden. Weitere Informationen finden Sie im Eintrag "überspringen und Entfernen von Ausnahmen in SQL Server 2000" in der [Problem](troubleshooting.md)Behandlung.

## <a name="object-materialization"></a>Objektmaterialisierung

Die Materialisierung erstellt CLR-Objekte aus Zeilen, die von einer oder mehreren SQL-Abfragen zurückgegeben werden.

- Die folgenden Aufrufe werden im Rahmen der Materialisierung *lokal ausgeführt* :

  - Konstruktoren

  - `ToString` Methoden in Projektionen

  - Typumwandlungen in Projektionen

- Methoden, die der <xref:System.Linq.Enumerable.AsEnumerable%2A>-Methode folgen, werden *lokal ausgeführt*. Diese Methode verursacht keine unmittelbare Ausführung.

- Sie können einen `struct` als Rückgabetyp eines Abfrageergebnisses oder als Member des Ergebnistyps verwenden. Entitäten müssen Klassen sein. Anonyme Typen werden als Klasseninstanzen materialisiert. Benannte structs (Nicht-Entitäten) können jedoch in Projektionen verwendet werden.

- Ein Member des Rückgabetyps eines Abfrageergebnisses kann vom Typ <xref:System.Linq.IQueryable%601> sein. Er wird als lokale Auflistung materialisiert.

- Die folgenden Methoden verursachen die *sofortige Materialisierung* der Sequenz, auf die die Methoden angewendet werden:

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a>Siehe auch

- [Verweis](reference.md)
- [Zurückgeben oder Überspringen von Elementen in einer Sequenz](return-or-skip-elements-in-a-sequence.md)
- [Verketten von zwei Sequenzen](concatenate-two-sequences.md)
- [Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen](return-the-set-difference-between-two-sequences.md)
- [Zurückgeben der Schnittmenge von zwei Sequenzen](return-the-set-intersection-of-two-sequences.md)
- [Zurückgeben der Vereinigungsmenge von zwei Sequenzen](return-the-set-union-of-two-sequences.md)
