---
title: Entity SQL-Referenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f92fbcf1aaa8f5d2c856fe1acdbc6d3886fa0c25
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="entity-sql-reference"></a>Entity SQL-Referenz
Dieser Abschnitt enthält [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-bezogene Referenzthemen. Dieses Thema fasst zusammen und gruppiert die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatoren nach Kategorie.  
  
## <a name="arithmetic-operators"></a>Arithmetische Operatoren  
 Arithmetische Operatoren führen mathematische Operationen an zwei Ausdrücken aus, die vom selben oder von unterschiedlichen numerischen Datentypen sind. In der folgenden Tabelle werden die arithmetischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operatoren aufgelistet.  
  
|Operator|Mit|  
|--------------|---------|  
|[+ (Addition)](../../../../../../docs/framework/data/adonet/ef/language-reference/add.md)|Addition.|  
|"/ (Division)"|Division.|  
|[% (Modulo)](../../../../../../docs/framework/data/adonet/ef/language-reference/modulo-entity-sql.md)|Gibt den Rest einer Division zurück.|  
|[* (Multiplikation)](../../../../../../docs/framework/data/adonet/ef/language-reference/multiply-entity-sql.md)|Multiplikation.|  
|[- (Negativ)](../../../../../../docs/framework/data/adonet/ef/language-reference/negative-entity-sql.md)|Negation.|  
|[- (Subtraktion)](../../../../../../docs/framework/data/adonet/ef/language-reference/subtract-entity-sql.md)|Subtraktion.|  
  
## <a name="canonical-functions"></a>Kanonische Funktionen  
 Kanonische Funktionen werden von allen Datenanbietern unterstützt und können von allen Abfragetechnologien verwendet werden. In der folgenden Tabelle sind die kanonischen Funktionen aufgeführt.  
  
|Funktion|Typ|  
|--------------|----------|  
|[Aggregieren Entity SQL kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|Erläutert die kanonischen Aggregatfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[Mathematische kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|Erläutert die kanonischen mathematischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[Kanonische Zeichenfolgefunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|Erläutert die kanonischen Zeichenfolgenfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[Kanonische Funktionen für Datum und Zeit](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Erläutert die kanonischen Datums- und Uhrzeitfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[Bitweise kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|Erläutert die kanonischen bitweisen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[Andere kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)|Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.|  
  
## <a name="comparison-operators"></a>Vergleichsoperatoren  
 Vergleichsoperatoren sind für die folgenden Typen definiert: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time` und `DateTimeOffset`. Für die Operanden wird vor der Anwendung des Vergleichsoperators eine implizite Typhöherstufung durchgeführt. Vergleichsoperatoren geben stets boolesche Werte zurück. Das Ergebnis ist `null`, wenn mindestens einer der Operanden den Wert `null` hat.  
  
 Gleichheit und Ungleichheit sind für jeden Objekttyp definiert, der über eine Identität verfügt, wie z. B. für den `Boolean`-Typ. Nicht primitive Objekte mit einer Identität werden als gleich betrachtet, wenn sie über die gleiche Identität verfügen. In der folgenden Tabelle werden die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Vergleichsoperatoren aufgelistet.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[= (Gleich)](../../../../../../docs/framework/data/adonet/ef/language-reference/equals-entity-sql.md)|Überprüft zwei Ausdrücke auf Gleichheit.|  
|[> (Größer als)](../../../../../../docs/framework/data/adonet/ef/language-reference/greater-than-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.|  
|[>= (Größer als oder gleich)](../../../../../../docs/framework/data/adonet/ef/language-reference/greater-than-or-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.|  
|[IS &#91;NOT&#93; NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/isnull-entity-sql.md)|Ermittelt, ob ein Abfrageausdruck den Wert NULL hat.|  
|[< (Kleiner als)](../../../../../../docs/framework/data/adonet/ef/language-reference/less-than-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.|  
|[<= (kleiner als oder gleich)](../../../../../../docs/framework/data/adonet/ef/language-reference/less-than-or-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist.|  
|[&#91; NICHT &#93; ZWISCHEN](../../../../../../docs/framework/data/adonet/ef/language-reference/between-entity-sql.md)|Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt.|  
|[!= (Ungleich)](../../../../../../docs/framework/data/adonet/ef/language-reference/not-equal-to-entity-sql.md)|Vergleicht zwei Ausdrücke, um zu ermitteln, ob sich der linke Ausdruck vom rechten Ausdruck unterscheidet.|  
|[&#91; NICHT &#93; MÖGEN](../../../../../../docs/framework/data/adonet/ef/language-reference/like-entity-sql.md)|Ermittelt, ob eine bestimmte Zeichenfolge mit einem angegebenen Muster übereinstimmt.|  
  
## <a name="logical-and-case-expression-operators"></a>Logische Operatoren und CASE-Ausdrucksoperatoren  
 Logische Operatoren testen den Wahrheitswert einer Bedingung. Der CASE-Ausdruck wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen. In der folgenden Tabelle sind die CASE-Ausdrucksoperatoren und die logischen Operatoren aufgeführt.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[& & (Logisches AND)](../../../../../../docs/framework/data/adonet/ef/language-reference/and-entity-sql.md)|Logisches AND.|  
|[! (Logisches NOT)](../../../../../../docs/framework/data/adonet/ef/language-reference/not-entity-sql.md)|Logisches 'NOT'|  
|[&#124; &#124; (Logisches OR)](../../../../../../docs/framework/data/adonet/ef/language-reference/or-entity-sql.md)|Logisches OR.|  
|[CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)|Wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.|  
|[THEN](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)|Das Ergebnis einer [Wenn](http://msdn.microsoft.com/en-us/6233fe9f-00b0-460e-8372-64e138a5f998) -Klausel, wenn sie auf "true" ausgewertet wird.|  
  
## <a name="query-operators"></a>Abfrageoperatoren  
 Abfrageoperatoren werden verwendet, um Abfrageausdrücke zu definieren, die Entitätsdaten zurückgeben. In der folgenden Tabelle werden die Abfrageoperatoren aufgelistet.  
  
|Operator|Mit|  
|--------------|---------|  
|[FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)|Gibt die Auflistung der im verwendete [wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) Anweisungen.|  
|[GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)|Gibt an, in die Objekte sind, die von einer Abfrage zurückgegebenen, Gruppen ([wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) platziert werden sollen.|  
|[GroupPartition](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md)|Gibt eine Auflistung von Argumentwerten zurück, die von der Gruppenpartition projiziert wurde, auf die sich das Aggregat bezieht.|  
|[HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)|Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.|  
|[LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)|Verwendet die [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) -Klausel zum physikalischen Paging.|  
|[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)|Gibt die Sortierreihenfolge, die zurückgegebenen Objekte verwendet, wird eine [wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) Anweisung.|  
|[SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)|Gibt die Elemente in der Projektion an, die von einer Abfrage zurückgegeben werden.|  
|[SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)|Verwendet die [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) -Klausel zum physikalischen Paging.|  
|[TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)|Gibt an, dass nur die erste Zeilengruppe aus dem Abfrageergebnis zurückgegeben wird.|  
|[WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md)|Filtert bedingt von einer Abfrage zurückgegebene Daten.|  
  
## <a name="reference-operators"></a>Verweisoperatoren  
 Ein Verweis ist ein logischer Zeiger (Fremdschlüssel) auf eine bestimmte Entität in einer bestimmten Entitätenmenge. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]unterstützt folgenden Operatoren zum Erstellen, löschen und Navigieren von verweisen.  
  
|Operator|Mit|  
|--------------|---------|  
|[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)|Erstellt Verweise auf eine Entität in einer Entitätenmenge.|  
|[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)|Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.|  
|[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)|Extrahiert den Schlüssel eines Verweises oder eines Entitätsausdrucks.|  
|[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)|Ermöglicht Ihnen, über die Beziehung von einem Entitätstyp zu einem anderen zu navigieren.|  
|[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)|Gibt einen Verweis auf eine Entitätsinstanz zurück.|  
  
## <a name="set-operators"></a>Set-Operatoren  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt eine Reihe von leistungsstarken Mengenoperatoren zur Verfügung. Dies schließt festgelegte ähnlich Transact-SQL-Operatoren, wie z. B. UNION, INTERSECT, EXCEPT und EXISTS. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt auch Operatoren zur Beseitigung von Duplikaten (SET), Mitgliedschaftstests (IN) und Verknüpfungen (JOIN). In der folgenden Tabelle werden die logischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Mengenoperatoren aufgelistet.  
  
|Operator|Mit|  
|--------------|---------|  
|[ANYELEMENT](../../../../../../docs/framework/data/adonet/ef/language-reference/anyelement-entity-sql.md)|Extrahiert ein Element aus einer mehrwertigen Auflistung.|  
|[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)|Gibt eine Auflistung der vom Abfrageausdruck auf der linken Seite des EXCEPT-Operanden zurückgegebenen und unterschiedlichen Werte zurück, die nicht zusätzlich vom Abfrageausdruck auf der rechten Seite des EXCEPT-Operanden zurückgegeben werden.|  
|[&#91; NICHT &#93; VORHANDEN IST](../../../../../../docs/framework/data/adonet/ef/language-reference/exists-entity-sql.md)|Bestimmt, ob eine Auflistung leer ist.|  
|[FLATTEN](../../../../../../docs/framework/data/adonet/ef/language-reference/flatten-entity-sql.md)|Konvertiert eine Auflistung von Auflistungen in eine vereinfachte Auflistung.|  
|[&#91;NOT&#93; IN](../../../../../../docs/framework/data/adonet/ef/language-reference/in-entity-sql.md)|Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.|  
|[INTERSECT](../../../../../../docs/framework/data/adonet/ef/language-reference/intersect-entity-sql.md)|Gibt eine Auflistung aller unterschiedlicher Werte zurück, die sowohl vom Abfrageausdruck auf der linken als auch dem auf der rechten Seite des INTERSECT-Operands zurückgegeben werden.|  
|[OVERLAPS](../../../../../../docs/framework/data/adonet/ef/language-reference/overlaps-entity-sql.md)|Bestimmt, ob zwei Auflistungen über gemeinsame Elemente verfügen.|  
|[SET](../../../../../../docs/framework/data/adonet/ef/language-reference/set-entity-sql.md)|Wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.|  
|[UNION](../../../../../../docs/framework/data/adonet/ef/language-reference/union-entity-sql.md)|Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.|  
  
## <a name="type-operators"></a>Typoperatoren  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]enthält die Vorgänge, die denen der Typ eines Ausdrucks (Werts) erstellt, abgefragt und bearbeitet werden. In der folgenden Tabelle sind Operatoren aufgeführt, die zum Arbeiten mit Typen verwendet werden.  
  
|Operator|Mit|  
|--------------|---------|  
|[CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)|Konvertiert einen Ausdruck von einem Datentyp in einen anderen.|  
|[COLLECTION](../../../../../../docs/framework/data/adonet/ef/language-reference/collection-entity-sql.md)|Verwendet eine [Funktion](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) Vorgang um eine Auflistung von Entitätstypen oder komplexen Typen zu deklarieren.|  
|[IS &#91;NOT&#93; OF](../../../../../../docs/framework/data/adonet/ef/language-reference/isof-entity-sql.md)|Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.|  
|[OFTYPE](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)|Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.|  
|[Konstruktoren benannter Typen](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)|Wird verwendet, um Instanzen von Entitätstypen oder komplexen Typen zu erstellen.|  
|[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)|Erstellt eine Instanz einer Multimenge aus einer Liste von Werten.|  
|[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)|Erstellt anonyme, strukturell typisierte Datensätze aus einem oder mehreren Werten.|  
|[TREAT](../../../../../../docs/framework/data/adonet/ef/language-reference/treat-entity-sql.md)|Behandelt ein Objekt eines bestimmten Basistyps als Objekt des angegebenen abgeleiteten Typs.|  
  
## <a name="other-operators"></a>Andere Operatoren  
 Die folgende Tabelle enthält andere [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatoren.  
  
|Operator|Mit|  
|--------------|---------|  
|[+ (Zeichenfolgenverkettung)](../../../../../../docs/framework/data/adonet/ef/language-reference/string-concatenation-entity-sql.md)|Wird zur Verkettung von Zeichenfolgen in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verwendet.|  
|[ (Memberzugriff)](../../../../../../docs/framework/data/adonet/ef/language-reference/member-access-entity-sql.md)|Wird verwendet, um auf den Wert einer Eigenschaft oder eines Feld einer Instanz des strukturellen konzeptionellen Modelltyps zuzugreifen.|  
|[-- (Kommentar)](../../../../../../docs/framework/data/adonet/ef/language-reference/comment-entity-sql.md)|Schließt [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Kommentare ein.|  
|[FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)|Definiert eine Inlinefunktion, die in einer Entity SQL-Abfrage ausgeführt werden kann.|  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL Language (Entity SQL-Sprache)](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
