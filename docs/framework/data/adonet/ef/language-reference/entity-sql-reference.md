---
title: Entity SQL-Referenz
ms.date: 03/30/2017
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
ms.openlocfilehash: 987aa5c05b88d684e050721077d704b29e546aab
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542123"
---
# <a name="entity-sql-reference"></a>Entity SQL-Referenz

Dieser Abschnitt enthält Entity SQL Referenz Artikel. In diesem Artikel werden die Entity SQL-Operatoren nach Kategorie zusammengefasst und gruppiert.

## <a name="arithmetic-operators"></a>Arithmetische operatoren

Arithmetische Operatoren führen mathematische Operationen an zwei Ausdrücken aus, die vom selben oder von unterschiedlichen numerischen Datentypen sind. In der folgenden Tabelle sind die Entity SQL arithmetischen Operatoren aufgelistet:

|Betreiber|Verwendung|
|--------------|---------|
|[+ (Addition)](add.md)|Addition.|
|[/ (Dividieren)](divide-entity-sql.md)|Division.|
|[% (Modulus)](modulo-entity-sql.md)|Gibt den Rest einer Division zurück.|
|[* (Multiplikation)](multiply-entity-sql.md)|Multiplikation.|
|[- (Negativ)](negative-entity-sql.md)|Negation.|
|[- (Subtraktion)](subtract-entity-sql.md)|Subtraktion.|

## <a name="canonical-functions"></a>Kanonische Funktionen

Kanonische Funktionen werden von allen Datenanbietern unterstützt und können von allen Abfragetechnologien verwendet werden. In der folgenden Tabelle sind die kanonischen Funktionen aufgelistet:

|Funktion|Typ|
|--------------|----------|
|[Aggregieren von kanonischen Funktionen (Entity SQL)](aggregate-canonical-functions.md)|Erläutert das Aggregieren Entity SQL kanonischen Funktionen.|
|[Kanonische Mathematikfunktionen](math-canonical-functions.md)|Erläutert die kanonischen Funktionen von Math Entity SQL.|
|[Kanonische Zeichenfolgefunktionen](string-canonical-functions.md)|Erläutert Zeichen folgen-Entity SQL kanonische Funktionen.|
|[Kanonische Funktionen für Datum und Zeit](date-and-time-canonical-functions.md)|Erläutert das Datum und die Uhrzeit Entity SQL kanonischen Funktionen.|
|[Bitweise kanonische Funktionen](bitwise-canonical-functions.md)|Erläutert bitweise Entity SQL kanonische Funktionen.|
|[Andere kanonische Funktionen](other-canonical-functions.md)|Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.|

## <a name="comparison-operators"></a>Vergleichsoperatoren

Vergleichsoperatoren sind für die folgenden Typen definiert: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time` und `DateTimeOffset`. Für die Operanden wird vor der Anwendung des Vergleichsoperators eine implizite Typhöherstufung durchgeführt. Vergleichsoperatoren geben stets boolesche Werte zurück. Das Ergebnis ist `null`, wenn mindestens einer der Operanden den Wert `null` hat.

Gleichheit und Ungleichheit sind für jeden Objekttyp definiert, der über eine Identität verfügt, wie z. B. für den `Boolean`-Typ. Nicht primitive Objekte mit einer Identität werden als gleich betrachtet, wenn sie über die gleiche Identität verfügen. In der folgenden Tabelle sind die Entity SQL Vergleichs Operatoren aufgelistet:

|Operator|BESCHREIBUNG|
|--------------|-----------------|
|[= (Ist gleich)](equals-entity-sql.md)|Überprüft zwei Ausdrücke auf Gleichheit.|
|[> (Greater Than) (> (Größer als))](greater-than-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.|
|[>= (Greater Than or Equal To) (>= (Größer als oder gleich)](greater-than-or-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.|
|[ist \[ nicht \] null](isnull-entity-sql.md)|Ermittelt, ob ein Abfrageausdruck den Wert NULL hat.|
|[< (Less Than) (< (Kleiner als))](less-than-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.|
|[<= (Less Than or Equal To) (<= (Kleiner als oder gleich))](less-than-or-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist.|
|[\[nicht \] zwischen](between-entity-sql.md)|Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt.|
|[\!= (Ungleich)](not-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu bestimmen, ob der linke Ausdruck nicht gleich dem rechten Ausdruck ist.|
|[\[nicht \] wie](like-entity-sql.md)|Bestimmt, ob eine bestimmte Zeichenfolge mit einem angegebenen Muster übereinstimmt.|

## <a name="logical-and-case-expression-operators"></a>Logische und CASE-Ausdrucks Operatoren

Logische Operatoren testen den Wahrheitswert einer Bedingung. Der CASE-Ausdruck wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen. In der folgenden Tabelle sind die Operatoren logischer und Case-Ausdruck aufgeführt:

|Operator|BESCHREIBUNG|
|--------------|-----------------|
|[&&  (logisches and)](and-entity-sql.md)|Logisches AND.|
|[\! (Logisches NOT)](not-entity-sql.md)|Logisches 'NOT'|
|[&#124;&#124;  (logisches OR)](or-entity-sql.md)|Logisches OR.|
|[CASE](case-entity-sql.md)|Wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.|
|[THEN](then-entity-sql.md)|Das Ergebnis einer [When](/previous-versions/dotnet/netframework-4.0/bb387119(v=vs.100)) -Klausel, wenn es als true ausgewertet wird.|

## <a name="query-operators"></a>Abfrageoperatoren

Abfrageoperatoren werden verwendet, um Abfrageausdrücke zu definieren, die Entitätsdaten zurückgeben. In der folgenden Tabelle sind die Abfrage Operatoren aufgelistet:

|Betreiber|Verwendung|
|--------------|---------|
|[FROM](from-entity-sql.md)|Gibt die Sammlung an, die in [Select](select-entity-sql.md) -Anweisungen verwendet wird.|
|[GROUP BY](group-by-entity-sql.md)|Gibt Gruppen an, in die Objekte eingefügt werden sollen, die von einem Abfrage Ausdruck ([Select](select-entity-sql.md)) zurückgegeben werden.|
|[GroupPartition](grouppartition-entity-sql.md)|Gibt eine Auflistung von Argumentwerten zurück, die von der Gruppenpartition projiziert wurde, auf die sich das Aggregat bezieht.|
|[HAVING](having-entity-sql.md)|Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.|
|[Ans](limit-entity-sql.md)|Wird mit der [Order by](order-by-entity-sql.md) -Klausel zum Ausführen physischer Paging verwendet.|
|[ORDER BY](order-by-entity-sql.md)|Gibt die Sortierreihenfolge für Objekte an, die in einer [Select](select-entity-sql.md) -Anweisung zurückgegeben werden.|
|[SELECT](select-entity-sql.md)|Gibt die Elemente in der Projektion an, die von einer Abfrage zurückgegeben werden.|
|[Überspringen](skip-entity-sql.md)|Wird mit der [Order by](order-by-entity-sql.md) -Klausel zum Ausführen physischer Paging verwendet.|
|[TOP](top-entity-sql.md)|Gibt an, dass nur die erste Zeilengruppe aus dem Abfrageergebnis zurückgegeben wird.|
|[WHERE](where-entity-sql.md)|Filtert bedingt von einer Abfrage zurückgegebene Daten.|

## <a name="reference-operators"></a>Verweis Operatoren

Ein Verweis ist ein logischer Zeiger (Fremdschlüssel) auf eine bestimmte Entität in einer bestimmten Entitätenmenge. Entity SQL unterstützt die folgenden Operatoren, um Verweise zu erstellen, zu konstruieren und durch diese zu navigieren:

|Betreiber|Verwendung|
|--------------|---------|
|[CREATEREF](createref-entity-sql.md)|Erstellt Verweise auf eine Entität in einer Entitätenmenge.|
|[DEREF](deref-entity-sql.md)|Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.|
|[KEY](key-entity-sql.md)|Extrahiert den Schlüssel eines Verweises oder eines Entitätsausdrucks.|
|[Umgehen](navigate-entity-sql.md)|Ermöglicht Ihnen, über die Beziehung von einem Entitätstyp zu einem anderen zu navigieren.|
|[Atur](ref-entity-sql.md)|Gibt einen Verweis auf eine Entitätsinstanz zurück.|

## <a name="set-operators"></a>Mengenoperatoren

Entity SQL bietet verschiedene leistungsstarke Set-Vorgänge. Dies schließt Mengen Operatoren ein, die Transact-SQL-Operatoren ähneln, z. b. Union, Intersect, außer und ist vorhanden. Entity SQL unterstützt auch Operatoren für die Eliminierung von Duplikaten (Set), das Testen von Mitgliedschaften (in) und Joins (Join). In der folgenden Tabelle sind die Entity SQL Set-Operatoren aufgelistet:

|Betreiber|Verwendung|
|--------------|---------|
|[ANYELEMENT](anyelement-entity-sql.md)|Extrahiert ein Element aus einer mehrwertigen Auflistung.|
|[EXCEPT](except-entity-sql.md)|Gibt eine Auflistung aller unterschiedlichen Werte aus dem Abfrage Ausdruck auf der linken Seite des außer-Operanden zurück, die nicht auch vom Abfrage Ausdruck auf der rechten Seite des außer-Operanden zurückgegeben werden.|
|[\[nicht \] vorhanden](exists-entity-sql.md)|Bestimmt, ob eine Auflistung leer ist.|
|[Vereinfachen](flatten-entity-sql.md)|Konvertiert eine Auflistung von Auflistungen in eine vereinfachte Auflistung.|
|[\[nicht \] in](in-entity-sql.md)|Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.|
|[INTERSECT](intersect-entity-sql.md)|Gibt eine Auflistung aller unterschiedlicher Werte zurück, die sowohl vom Abfrageausdruck auf der linken als auch dem auf der rechten Seite des INTERSECT-Operands zurückgegeben werden.|
|[OVERLAPS](overlaps-entity-sql.md)|Bestimmt, ob zwei Auflistungen über gemeinsame Elemente verfügen.|
|[SET](set-entity-sql.md)|Wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.|
|[UNION](union-entity-sql.md)|Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.|

## <a name="type-operators"></a>Typoperatoren

Entity SQL stellt Vorgänge bereit, mit denen der Typ eines Ausdrucks (Werts) erstellt, abgefragt und bearbeitet werden kann. In der folgenden Tabelle sind die Operatoren aufgelistet, die für die Arbeit mit Typen verwendet werden:

|Betreiber|Verwendung|
|--------------|---------|
|[CAST](cast-entity-sql.md)|Konvertiert einen Ausdruck von einem Datentyp in einen anderen.|
|[Ausstellung](collection-entity-sql.md)|Wird in einem [Funktions](function-entity-sql.md) Vorgang verwendet, um eine Auflistung von Entitäts Typen oder komplexen Typen zu deklarieren.|
|[ist \[ nicht \] von](isof-entity-sql.md)|Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.|
|[OfType](oftype-entity-sql.md)|Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.|
|[Konstruktoren benannter Typen](named-type-constructor-entity-sql.md)|Wird verwendet, um Instanzen von Entitätstypen oder komplexen Typen zu erstellen.|
|[MULTISET](multiset-entity-sql.md)|Erstellt eine Instanz einer Multimenge aus einer Liste von Werten.|
|[ROW](row-entity-sql.md)|Erstellt anonyme, strukturell typisierte Datensätze aus einem oder mehreren Werten.|
|[TREAT](treat-entity-sql.md)|Behandelt ein Objekt eines bestimmten Basistyps als Objekt des angegebenen abgeleiteten Typs.|

## <a name="other-operators"></a>Andere Operatoren

In der folgenden Tabelle sind andere Entity SQL-Operatoren aufgelistet:

|Betreiber|Verwendung|
|--------------|---------|
|[+ (Zeichenfolgenverkettung)](string-concatenation-entity-sql.md)|Wird verwendet, um Zeichen folgen in Entity SQL zu verketten.|
|[. (Member Access)](member-access-entity-sql.md)|Wird verwendet, um auf den Wert einer Eigenschaft oder eines Feld einer Instanz des strukturellen konzeptionellen Modelltyps zuzugreifen.|
|[-- (Kommentar)](comment-entity-sql.md)|Fügen Sie Entity SQL Kommentare ein.|
|[FUNCTION](function-entity-sql.md)|Definiert eine Inlinefunktion, die in einer Entity SQL-Abfrage ausgeführt werden kann.|

## <a name="see-also"></a>Siehe auch

- [Entity SQL-Sprache](entity-sql-language.md)
