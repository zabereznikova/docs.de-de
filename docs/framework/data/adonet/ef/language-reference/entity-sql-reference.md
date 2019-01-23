---
title: Entity SQL-Referenz
ms.date: 03/30/2017
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
ms.openlocfilehash: 75f9c61a24ffdcba890ae04ccc5c656460c13088
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522153"
---
# <a name="entity-sql-reference"></a>Entity SQL-Referenz

Dieser Abschnitt enthält die Entity SQL-Referenzartikel. In diesem Artikel werden zusammengefasst und die Entity SQL-Operatoren nach ihrer Kategorie gruppiert.

## <a name="arithmetic-operators"></a>Arithmetische Operatoren

Arithmetische Operatoren führen mathematische Operationen an zwei Ausdrücken aus, die vom selben oder von unterschiedlichen numerischen Datentypen sind. Die folgende Tabelle enthält die Entity SQL arithmetischen Operatoren:

|Operator|Mit|
|--------------|---------|
|[+ (Addition)](add.md)|Addition.|
|[/ (Division)](divide-entity-sql.md)|Division.|
|[% (Modulo)](modulo-entity-sql.md)|Gibt den Rest einer Division zurück.|
|[* (Multiplikation)](multiply-entity-sql.md)|Multiplikation.|
|[- (Negativ)](negative-entity-sql.md)|Negation.|
|[- (Subtraktion)](subtract-entity-sql.md)|Subtraktion.|

## <a name="canonical-functions"></a>Kanonische Funktionen

Kanonische Funktionen werden von allen Datenanbietern unterstützt und können von allen Abfragetechnologien verwendet werden. In der folgende Tabelle sind die kanonischen Funktionen aufgeführt:

|Funktion|Typ|
|--------------|----------|
|[Gesamtentität SQL kanonische Funktionen](aggregate-canonical-functions.md)|Erläutert die aggregierte kanonische Entity SQL-Funktionen.|
|[Mathematische kanonische Funktionen](math-canonical-functions.md)|Beschreibt kanonische mathematische Entity SQL-Funktionen.|
|[Kanonische Zeichenfolgefunktionen](string-canonical-functions.md)|Erläutert die kanonische Zeichenfolgenfunktionen für Entity SQL.|
|[Kanonische Funktionen für Datum und Zeit](date-and-time-canonical-functions.md)|Beschreibt Datums- / kanonische Entity SQL-Funktionen.|
|[Bitweise kanonische Funktionen](bitwise-canonical-functions.md)|Erläutert die bitweise kanonische Entity SQL-Funktionen.|
|[Andere kanonische Funktionen](other-canonical-functions.md)|Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.|

## <a name="comparison-operators"></a>Vergleichsoperatoren

Vergleichsoperatoren sind für die folgenden Typen definiert: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time` und `DateTimeOffset`. Für die Operanden wird vor der Anwendung des Vergleichsoperators eine implizite Typhöherstufung durchgeführt. Vergleichsoperatoren geben stets boolesche Werte zurück. Das Ergebnis ist `null`, wenn mindestens einer der Operanden den Wert `null` hat.

Gleichheit und Ungleichheit sind für jeden Objekttyp definiert, der über eine Identität verfügt, wie z. B. für den `Boolean`-Typ. Nicht primitive Objekte mit einer Identität werden als gleich betrachtet, wenn sie über die gleiche Identität verfügen. Die folgende Tabelle enthält die Entity SQL-Vergleichsoperatoren:

|Operator|Beschreibung|
|--------------|-----------------|
|[= (Gleich)](equals-entity-sql.md)|Überprüft zwei Ausdrücke auf Gleichheit.|
|[> (Größer als)](greater-than-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.|
|[>= (Größer als oder gleich)](greater-than-or-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.|
|[IST \[NICHT\] NULL](isnull-entity-sql.md)|Ermittelt, ob ein Abfrageausdruck den Wert NULL hat.|
|[< (Kleiner als)](less-than-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.|
|[<= (kleiner als oder gleich)](less-than-or-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist.|
|[\[NICHT\] BETWEEN](between-entity-sql.md)|Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt.|
|[\!= (Ungleich)](not-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu bestimmen, ob der linke Ausdruck ungleich dem rechten Ausdruck ist nicht an.|
|[\[NICHT\] WIE](like-entity-sql.md)|Ermittelt, ob eine bestimmte Zeichenfolge mit einem angegebenen Muster übereinstimmt.|

## <a name="logical-and-case-expression-operators"></a>Logische Operatoren und Case-Ausdrucksoperatoren

Logische Operatoren testen den Wahrheitswert einer Bedingung. Der CASE-Ausdruck wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen. Die folgende Tabelle enthält die logische Operatoren und CASE-Ausdrucksoperatoren:

|Operator|Beschreibung|
|--------------|-----------------|
|[& & (Logisches AND)](and-entity-sql.md)|Logisches AND.|
|[\! (Logisches NOT)](not-entity-sql.md)|Logisches 'NOT'|
|[&#124;&#124; (Logical OR)](or-entity-sql.md)|Logisches OR.|
|[CASE](case-entity-sql.md)|Wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.|
|[THEN](then-entity-sql.md)|Das Ergebnis einer [beim](https://msdn.microsoft.com/library/6233fe9f-00b0-460e-8372-64e138a5f998) -Klausel, wenn er auf "true" ausgewertet wird.|

## <a name="query-operators"></a>Abfrageoperatoren

Abfrageoperatoren werden verwendet, um Abfrageausdrücke zu definieren, die Entitätsdaten zurückgeben. In der folgende Tabelle werden die Abfrageoperatoren aufgelistet:

|Operator|Mit|
|--------------|---------|
|[FROM](from-entity-sql.md)|Gibt die Auflistung, die in dient [wählen](select-entity-sql.md) Anweisungen.|
|[GROUP BY](group-by-entity-sql.md)|Gibt an, Gruppen, die in die Objekte, die von einer Abfrage zurückgegeben werden ([wählen](select-entity-sql.md)) platziert werden sollen.|
|[GroupPartition](grouppartition-entity-sql.md)|Gibt eine Auflistung von Argumentwerten zurück, die von der Gruppenpartition projiziert wurde, auf die sich das Aggregat bezieht.|
|[HAVING](having-entity-sql.md)|Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.|
|[LIMIT](limit-entity-sql.md)|Verwendung der [ORDER BY](order-by-entity-sql.md) -Klausel zum physikalischen Paging.|
|[ORDER BY](order-by-entity-sql.md)|Gibt die Sortierreihenfolge, die zurückgegebenen Objekte dient eine [wählen](select-entity-sql.md) Anweisung.|
|[SELECT](select-entity-sql.md)|Gibt die Elemente in der Projektion an, die von einer Abfrage zurückgegeben werden.|
|[SKIP](skip-entity-sql.md)|Verwendung der [ORDER BY](order-by-entity-sql.md) -Klausel zum physikalischen Paging.|
|[TOP](top-entity-sql.md)|Gibt an, dass nur die erste Zeilengruppe aus dem Abfrageergebnis zurückgegeben wird.|
|[WHERE](where-entity-sql.md)|Filtert bedingt von einer Abfrage zurückgegebene Daten.|

## <a name="reference-operators"></a>Verweisoperatoren

Ein Verweis ist ein logischer Zeiger (Fremdschlüssel) auf eine bestimmte Entität in einer bestimmten Entitätenmenge. Entity SQL unterstützt folgenden Operatoren zum Erstellen, löschen und Navigieren von verweisen:

|Operator|Mit|
|--------------|---------|
|[CREATEREF](createref-entity-sql.md)|Erstellt Verweise auf eine Entität in einer Entitätenmenge.|
|[DEREF](deref-entity-sql.md)|Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.|
|[KEY](key-entity-sql.md)|Extrahiert den Schlüssel eines Verweises oder eines Entitätsausdrucks.|
|[NAVIGATE](navigate-entity-sql.md)|Ermöglicht Ihnen, über die Beziehung von einem Entitätstyp zu einem anderen zu navigieren.|
|[REF](ref-entity-sql.md)|Gibt einen Verweis auf eine Entitätsinstanz zurück.|

## <a name="set-operators"></a>Mengenoperatoren

Entity SQL stellt verschiedene von leistungsstarken Mengenoperatoren bereit. Dies schließt festgelegte ähnlich Transact-SQL-Operatoren wie z. B. UNION, INTERSECT, EXCEPT und EXISTS. Entity SQL unterstützt auch Operatoren für Duplikaten (SET), mitgliedschaftstests (IN) und Joins (JOIN). Die folgende Tabelle enthält die Entity SQL-Set-Operatoren:

|Operator|Mit|
|--------------|---------|
|[ANYELEMENT](anyelement-entity-sql.md)|Extrahiert ein Element aus einer mehrwertigen Auflistung.|
|[EXCEPT](except-entity-sql.md)|Gibt eine Auflistung aller unterschiedlicher Werte vom Abfrageausdruck auf der linken Seite des EXCEPT-Operanden, die auch vom Abfrageausdruck auf der rechten Seite des EXCEPT-Operanden zurückgegeben werden nicht zurück.|
|[\[NICHT\] EXISTS](exists-entity-sql.md)|Bestimmt, ob eine Auflistung leer ist.|
|[FLATTEN](flatten-entity-sql.md)|Konvertiert eine Auflistung von Auflistungen in eine vereinfachte Auflistung.|
|[\[NICHT\] IN](in-entity-sql.md)|Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.|
|[INTERSECT](intersect-entity-sql.md)|Gibt eine Auflistung aller unterschiedlicher Werte zurück, die sowohl vom Abfrageausdruck auf der linken als auch dem auf der rechten Seite des INTERSECT-Operands zurückgegeben werden.|
|[OVERLAPS](overlaps-entity-sql.md)|Bestimmt, ob zwei Auflistungen über gemeinsame Elemente verfügen.|
|[SET](set-entity-sql.md)|Wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.|
|[UNION](union-entity-sql.md)|Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.|

## <a name="type-operators"></a>Typoperatoren

Entity SQL stellt Operationen, mit denen der Typ eines Ausdrucks (Werts) erstellt, abgefragt und bearbeitet werden kann, bereit. Die folgende Tabelle enthält die Operatoren, die zum Arbeiten mit Typen verwendet werden:

|Operator|Mit|
|--------------|---------|
|[CAST](cast-entity-sql.md)|Konvertiert einen Ausdruck von einem Datentyp in einen anderen.|
|[COLLECTION](collection-entity-sql.md)|Verwendet eine [Funktion](function-entity-sql.md) Vorgang um eine Auflistung von Entitätstypen oder komplexen Typen zu deklarieren.|
|[IS \[NOT\] OF](isof-entity-sql.md)|Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.|
|[OFTYPE](oftype-entity-sql.md)|Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.|
|[Konstruktoren benannter Typen](named-type-constructor-entity-sql.md)|Wird verwendet, um Instanzen von Entitätstypen oder komplexen Typen zu erstellen.|
|[MULTISET](multiset-entity-sql.md)|Erstellt eine Instanz einer Multimenge aus einer Liste von Werten.|
|[ROW](row-entity-sql.md)|Erstellt anonyme, strukturell typisierte Datensätze aus einem oder mehreren Werten.|
|[TREAT](treat-entity-sql.md)|Behandelt ein Objekt eines bestimmten Basistyps als Objekt des angegebenen abgeleiteten Typs.|

## <a name="other-operators"></a>Andere Operatoren

Die folgende Tabelle enthält die anderen Entity SQL-Operatoren:

|Operator|Mit|
|--------------|---------|
|[+ (Zeichenfolgenverkettung)](string-concatenation-entity-sql.md)|Zum Verketten von Zeichenfolgen in Entity SQL verwendet.|
|[. (Memberzugriff)](member-access-entity-sql.md)|Wird verwendet, um auf den Wert einer Eigenschaft oder eines Feld einer Instanz des strukturellen konzeptionellen Modelltyps zuzugreifen.|
|[-- (Kommentar)](comment-entity-sql.md)|Entity SQL-Kommentare einschließen.|
|[FUNCTION](function-entity-sql.md)|Definiert eine Inlinefunktion, die in einer Entity SQL-Abfrage ausgeführt werden kann.|

## <a name="see-also"></a>Siehe auch

- [Entity SQL Language (Entity SQL-Sprache)](entity-sql-language.md)
