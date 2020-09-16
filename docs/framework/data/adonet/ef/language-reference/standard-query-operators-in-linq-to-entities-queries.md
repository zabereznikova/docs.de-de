---
title: Standardabfrageoperatoren in LINQ to Entities-Abfragen
ms.date: 08/21/2018
ms.assetid: 7fa55a9b-6219-473d-b1e5-2884a32dcdff
ms.openlocfilehash: a61296d924ab1ff32b5bee523d6f0a06dda95db3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557774"
---
# <a name="standard-query-operators-in-linq-to-entities-queries"></a>Standardabfrageoperatoren in LINQ to Entities-Abfragen
In einer Abfrage geben Sie die Informationen an, die aus der Datenquelle abgerufen werden sollen. In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden. LINQ stellt eine Reihe von Standardabfragemethoden für die Verwendung in einer Abfrage bereit. Die meisten dieser Methoden arbeiten mit Sequenzen. in diesem Kontext ist eine Sequenz ein Objekt, dessen Typ die- <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle oder die- <xref:System.Linq.IQueryable%601> Schnittstelle implementiert. Die Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation, Sortierung, Gruppierung, Paging und mehr bereit. Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax, sodass sie mithilfe von Abfrageausdruckssyntax aufgerufen werden können. Mit einem Abfrageausdruck kann eine Abfrage besser lesbar ausgedrückt werden als mit dessen methodenbasierter Entsprechung. Die Abfrageausdrucksklauseln werden bei der Kompilierung in Aufrufe der Abfragemethoden übersetzt. Eine Liste der Standard Abfrage Operatoren, die über äquivalente Abfrage Ausdrucks Klauseln verfügen, finden Sie unter [Übersicht über Standard Abfrage Operatoren](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).  
  
 Nicht alle Standard Abfrage Operatoren werden in LINQ to Entities Abfragen unterstützt. Weitere Informationen finden Sie [unter Unterstützte und nicht unterstützte LINQ-Methoden (LINQ to Entities)](supported-and-unsupported-linq-methods-linq-to-entities.md). Dieses Thema enthält Informationen zu den-Standard Abfrage Operatoren, die für LINQ to Entities spezifisch sind. Weitere Informationen zu bekannten Problemen in LINQ to Entities Abfragen finden Sie unter [bekannte Probleme und Überlegungen in LINQ to Entities](known-issues-and-considerations-in-linq-to-entities.md).  
  
## <a name="projection-and-filtering-methods"></a>Projektions- und Filtermethoden  
 *Projektion* bezieht sich auf das Transformieren der Elemente eines Resultsets in eine gewünschte Form. Beispielsweise kann eine Teilmenge der benötigten Eigenschaften der einzelnen Objekte im Resultset projiziert werden, es kann eine Eigenschaft projiziert werden, um eine mathematische Berechnung damit auszuführen, oder es kann das ganze Objekt aus dem Resultset projiziert werden. Zur Projektion werden die `Select`-Methode und die `SelectMany`-Methode verwendet.  
  
 *Filterung* bezieht sich auf den Vorgang, bei dem das Resultset auf die Elemente beschränkt wird, die einer bestimmten Bedingung entsprechen. Zum Filtern wird die `Where`-Methode verwendet.  
  
 Die meisten über Ladungen der Projektions-und Filter Methoden werden in LINQ to Entities unterstützt, mit Ausnahme derjenigen, die ein Positions Argument akzeptieren.  
  
## <a name="join-methods"></a>Methoden zur Verknüpfung  
 Das Verknüpfen ist eine wichtige Operation bei Abfragen von Daten aus Datenquellen, die nicht über navigierbare Beziehungen verfügen. Eine Verknüpfung zweier Datenquellen ist die Zuordnung von Objekten der einen Datenquelle zu Objekten in der anderen Datenquelle, die über ein gemeinsames Attribut oder eine gemeinsame Eigenschaft verfügen. Zur Verknüpfung werden die `Join`-Methode und die `GroupJoin`-Methode verwendet.  
  
 Die meisten Überladungen der Methoden zur Verknüpfung werden unterstützt. Davon ausgenommen sind Methoden, die einen <xref:System.Collections.Generic.IEqualityComparer%601> verwenden. Der Grund dafür ist, dass der Vergleich nicht für die Datenquelle übersetzt werden kann.  
  
## <a name="set-methods"></a>Methoden für Mengen  
 Mengenoperationen in LINQ sind Abfrageoperationen, deren Resultsets auf der Gegenwart oder Abwesenheit äquivalenter Elemente in derselben oder in einer anderen Auflistung (oder Menge) basieren. Für Mengen werden die Methoden `All`, `Any`, `Concat`, `Contains`, `DefaultIfEmpty`, `Distinct`, `EqualAll`, `Except`, `Intersect` und `Union` verwendet.  
  
 Die meisten über Ladungen der Set-Methoden werden in LINQ to Entities unterstützt, es gibt jedoch einige Unterschiede im Verhalten im Vergleich zu LINQ to Objects. Set-Methoden, die einen verwenden, <xref:System.Collections.Generic.IEqualityComparer%601> werden jedoch nicht unterstützt, da der Vergleich nicht in die Datenquelle übersetzt werden kann.  
  
## <a name="ordering-methods"></a>Sortiermethoden  
 Mit Sortierung wird das auf einem oder mehreren Attributen basierende Sortieren von Elementen eines Resultsets bezeichnet. Durch die Angabe eines oder mehrerer Sortierkriterien können Verbindungen innerhalb einer Gruppe aufgelöst werden.  
  
 Die meisten Überladungen der Sortiermethoden werden unterstützt. Davon ausgenommen sind Methoden, die einen <xref:System.Collections.Generic.IComparer%601> verwenden. Der Grund dafür ist, dass der Vergleich nicht für die Datenquelle übersetzt werden kann. Zum Sortieren werden die Methoden `OrderBy`, `OrderByDescending`, `ThenBy`, `ThenByDescending` und `Reverse` verwendet.  
  
 Da die Abfrage für die Datenquelle ausgeführt wird, kann sich das Sortierverhalten von den Abfragen unterscheiden, die in der CLR ausgeführt werden. Der Grund dafür ist, dass in der Datenquelle Sortieroptionen wie Fallsortierung, Kanjisortierung und Nullsortierung festgelegt werden können. Je nach Datenquelle können diese Sortieroptionen zu anderen Ergebnissen als in der CLR führen.  
  
 Wenn dieselbe Schlüsselauswahlfunktion in mehr als einem Sortiervorgang angegeben wird, wird eine doppelte Sortierung ausgeführt. Da dies nicht gültig ist, wird eine Ausnahme ausgelöst.  
  
## <a name="grouping-methods"></a>Gruppierungsmethoden  
 Mit Gruppierung wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen. Zum Gruppieren wird die `GroupBy`-Methode verwendet.  
  
 Die meisten Überladungen der Gruppierungsmethoden werden unterstützt. Davon ausgenommen sind Methoden, die einen <xref:System.Collections.Generic.IEqualityComparer%601> verwenden. Der Grund dafür ist, dass der Vergleich nicht für die Datenquelle übersetzt werden kann.  
  
 Die Gruppierungsmethoden werden der Datenquelle mithilfe einer eigenen Unterabfrage für die Schlüsselauswahlfunktion zugeordnet. Die Unterabfrage für den Vergleich mit der Schlüsselauswahlfunktion wird unter Verwendung der Semantik der Datenquelle ausgeführt. Dies ist beispielsweise beim Vergleich von `null`-Werten bedeutsam.  
  
## <a name="aggregate-methods"></a>Aggregatmethoden  
 Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet. Ein Beispiel für einen Aggregationsvorgang ist die Berechnung der durchschnittlichen Tagestemperatur aus den Tagestemperaturen eines Monats. Für die Aggregation werden die Methoden `Aggregate`, `Average`, `Count`, `LongCount`, `Max`, `Min` und `Sum` verwendet.  
  
 Die meisten Überladungen der Aggregatmethoden werden unterstützt. Das Verhalten der Aggregatmethoden bzgl. NULL-Werten wird durch die Semantik der Datenquelle gesteuert. Das Verhalten der Aggregatmethoden im Zusammenhang mit NULL-Werten ist je nach verwendeter Backenddatenquelle unterschiedlich. Das Verhalten der Aggregatmethoden, das die Semantik der Datenquelle verwendet, kann sich auch von dem von CLR-Methoden erwarteten Verhalten unterscheiden. Beim Standardverhalten der `Sum`-Methode in SQL Server werden beispielsweise NULL-Werte ignoriert und keine Ausnahmen ausgelöst.  
  
 Sämtliche bei einer Aggregation ausgelösten Ausnahmen, wie ein Überlauf der `Sum`-Funktion, werden als Datenquellenausnahmen oder Entity Framework-Ausnahmen während der Materialisierung der Abfrageergebnisse ausgelöst.  
  
 Für Methoden, die eine Berechnung aus einer Sequenz beinhalten, wie `Sum` oder `Average`, wird die eigentliche Berechnung auf dem Server ausgeführt. Daher können Typkonvertierungen und Präzisionsverlust auf dem Server auftreten, und die Ergebnisse können sich von denen, die bei der Verwendung der CLR-Semantik zu erwarten sind, unterscheiden.  
  
 Das Standardverhalten der Aggregatmethoden für NULL-Werte und Werte, die von NULL verschieden sind, wird in der folgenden Tabelle dargestellt:  
  
|Methode|Keine Daten|Alle NULL-Werte|Einige NULL-Werte|Keine NULL-Werte|  
|------------|-------------|---------------------|----------------------|--------------------|  
|`Average`|Gibt NULL zurück.|Gibt NULL zurück.|Gibt den Durchschnitt der von NULL verschiedenen Werte in einer Sequenz zurück.|Berechnet den Durchschnitt einer Sequenz von numerischen Werten.|  
|`Count`|Gibt 0 (null) zurück|Gibt die Anzahl der NULL-Werte in der Sequenz zurück.|Gibt die Anzahl der NULL-Werte und der von NULL verschiedenen Werte in einer Sequenz zurück.|Gibt die Anzahl der Elemente in der Sequenz zurück.|  
|`Max`|Gibt NULL zurück.|Gibt NULL zurück.|Gibt den maximalen von NULL verschiedenen Wert in einer Sequenz zurück.|Gibt den Maximalwert in einer Sequenz zurück.|  
|`Min`|Gibt NULL zurück.|Gibt NULL zurück.|Gibt den minimalen von NULL verschiedenen Wert in einer Sequenz zurück.|Gibt den Minimalwert in einer Sequenz zurück.|  
|`Sum`|Gibt NULL zurück.|Gibt NULL zurück.|Gibt die Summe der von NULL verschiedenen Werte in einer Sequenz zurück.|Berechnet die Summe einer Sequenz von numerischen Werten.|  
  
## <a name="type-methods"></a>Typmethoden  
 Beide LINQ-Methoden, die mit Typkonvertierung und-Tests zu tun haben, werden im Kontext der Entity Framework unterstützt. Dies bedeutet, dass es sich bei den einzigen unterstützten Typen um Typen handelt, die dem entsprechenden Entity Framework Typ zugeordnet werden. Eine Liste dieser Typen finden Sie unter [konzeptionelle Modelltypen (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl). Als Typmethoden werden `Convert` und `OfType` verwendet.  
  
 `OfType` wird für Entitätstypen unterstützt. `Convert` wird für primitive Typen in einem konzeptionellen Modell unterstützt.  Die C#-Methoden `is` und `as` werden ebenfalls unterstützt.  
  
## <a name="paging-methods"></a>Pagingmethoden  
 Paging-Vorgänge geben ein einzelnes Element oder mehrere Elemente aus einer Sequenz zurück. Die unterstützten Paging-Methoden sind `First` , `FirstOrDefault` , `Single` , `SingleOrDefault` , `Skip` und `Take` .  
  
 Eine Reihe von Pagingmethoden werden nicht unterstützt, da Funktionen nicht der Datenquelle zugeordnet werden können oder nicht die implizite Reihenfolge von Sätzen in der Datenquelle. Methoden, die einen Standardwert zurückgeben, sind auf primitive Typen in einem konzeptionellen Modell und Referenztypen mit dem Standardwert NULL beschränkt. Pagingmethoden, die für eine leere Sequenz ausgeführt werden, geben NULL zurück.  
  
## <a name="see-also"></a>Siehe auch

- [Unterstützte und nicht unterstützte LINQ-Methoden (LINQ to Entities)](supported-and-unsupported-linq-methods-linq-to-entities.md)
- [Übersicht über Standardabfrageoperatoren](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120))
