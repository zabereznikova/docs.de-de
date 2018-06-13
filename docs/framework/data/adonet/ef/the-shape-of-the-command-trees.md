---
title: Form der Befehlsstrukturen
ms.date: 03/30/2017
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
ms.openlocfilehash: 9084e2616ac4ea540bdf755afd011d67a5c991fa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766035"
---
# <a name="the-shape-of-the-command-trees"></a>Form der Befehlsstrukturen
Das SQL-Generierungsmodul generiert anhand eines angegebenen Eingabeabfragebefehlsstruktur-Ausdrucks eine Back-End-spezifische SQL-Abfrage. In diesem Abschnitt werden die Merkmale, die Eigenschaften und die Struktur der Abfragebefehlsstrukturen erläutert.  
  
## <a name="query-command-trees-overview"></a>Übersicht über die Abfragebefehlsstrukturen  
 Bei einer Abfragebefehlsstruktur handelt es sich um die Objektmodelldarstellung einer Abfrage. Abfragebefehlsstrukturen dienen zwei Zwecken:  
  
-   Dem Ausdrücken einer Eingabeabfrage für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Dem Ausdrücken eine Ausgabeabfrage, die einem Anbieter übergeben wird und eine Back-End-Abfrage beschreibt.  
  
 Abfragebefehlsstrukturen unterstützen eine umfangreichere Semantik als SQL:1999-kompatible Abfragen. Dies umfasst die Unterstützung von geschachtelten Auflistungen und Typvorgängen, z. B. bei der Prüfung, ob es sich bei einer Entität um einen bestimmten Typ handelt, oder beim Filtern von Sätzen anhand eines Typs.  
  
 Die "DBQueryCommandTree.Query"-Eigenschaft ist der Stamm der Ausdrucksstruktur, die die Abfragelogik beschreibt. Die "DBQueryCommandTree.Parameters"-Eigenschaft enthält eine Liste der in der Abfrage verwendeten Parameter. Die Ausdrucksstruktur besteht aus "DbExpression"-Objekten.  
  
 Ein "DbExpression"-Objekt stellt eine Berechnung dar. Zum Verfassen von Abfrageausdrücken werden in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verschiedene Ausdrucksarten bereitgestellt, darunter Konstanten, Variablen, Funktionen, Konstruktoren und relationale Standardoperatoren, wie z. B. Filter und Join. Alle "DbExpression"-Objekt verfügt über eine ResultType-Eigenschaft, die den Typ des von diesem Ausdruck erzeugten Ergebnisses darstellt. Dieser Typ wird als "TypeUsage" ausgedrückt.  
  
## <a name="shapes-of-the-output-query-command-tree"></a>Formen der Ausgabeabfrage-Befehlsstruktur  
 Ausgabeabfrage-Befehlsstrukturen entsprechen relationalen (SQL-)Abfragen und unterliegen weitaus strengeren Regeln als Abfragebefehlsstrukturen. In der Regel enthalten sie Konstrukte, die einfach in SQL übersetzt werden können.  
  
 Eingabebefehlsstrukturen werden für das konzeptionelle Modell ausgedrückt, das Navigationseigenschaften, Zuordnungen zwischen Entitäten und Vererbung unterstützt. Ausgabebefehlsstrukturen werden für das Speichermodell ausgedrückt. Mit Eingabebefehlsstrukturen können geschachtelte Auflistungen projiziert werden, nicht jedoch mit Ausgabebefehlsstrukturen.  
  
 Ausgabeabfrage-Befehlsstrukturen beruhen auf einer Teilmenge der verfügbaren "DbExpression"-Objekte. Selbst einige der Ausdrücke dieser Teilmenge unterliegen einer eingeschränkten Verwendung.  
  
 Typvorgänge, wie z. B. das Überprüfen, ob es sich bei einem angegebenen Ausdruck um einen bestimmten Typ handelt, oder das Filtern von Sätzen anhand eines Typs, sind in Ausgabebefehlsstrukturen nicht vorhanden.  
  
 In Ausgabebefehlsstrukturen werden für Projektionen nur Ausdrücke verwendet, die boolesche Werte zurückgeben. Dies gilt nur für Prädikate in Ausdrücken, die ein Prädikat, wie z. B. eine Filter- oder eine Case-Anweisung erfordern.  
  
 Der Stamm einer Ausgabeabfrage-Befehlsstruktur ist ein "DbProjectExpression"-Objekt.  
  
### <a name="expression-types-not-present-in-output-query-command-trees"></a>Nicht in Ausgabeabfrage-Befehlsstrukturen vorhandene Ausdrücke  
 Die folgenden Ausdruckstypen sind in einer Ausgabeabfrage-Befehlsstruktur nicht gültig und müssen nicht von Anbietern behandelt werden:  
  
 DbDerefExpression  
  
 DbEntityRefExpression  
  
 DbRefKeyExpression  
  
 DbIsOfExpression  
  
 DbOfTypeExpression  
  
 DbRefExpression  
  
 DbRelationshipNavigationExpression  
  
 DbTreatExpression  
  
### <a name="expression-restrictions-and-notes"></a>Ausdruckseinschränkungen und Hinweise  
 Viele Ausdrücke können nur eingeschränkt in Ausgabeabfrage-Befehlsstrukturen verwendet werden:  
  
#### <a name="dbfunctionexpression"></a>DbFunctionExpression  
 Die folgenden Funktionstypen können übergeben werden:  
  
-   Kanonische Funktionen, die vom EDM-Namespace erkannt werden.  
  
-   Integrierte (Speicher-)Funktionen, die von "BuiltInAttribute" erkannt werden.  
  
-   Benutzerdefinierte Funktionen.  
  
 Kanonische Funktionen (finden Sie unter [kanonische Funktionen](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) für Weitere Informationen) angegeben sind, als Teil der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], und Anbieter sollten die Implementierungen für kanonische Funktionen, die basierend auf diesen Spezifikationen angeben. Speicherfunktionen beruhen auf den Spezifikationen des entsprechenden Anbietermanifests. Benutzerdefinierte Funktionen beruhen auf den SSDL-Spezifikationen.  
  
 Zudem verfügen Funktionen mit dem NiladicFunction-Attribut nicht über Argumente und sollten ohne die Klammer am Ende übersetzt werden.  Das heißt,  *\<Funktionsname >* anstelle von  *\<FunctionName > ()*.  
  
#### <a name="dbnewinstanceexpression"></a>DbNewInstanceExpression  
 "DbNewInstanceExpression" kann nur in den folgenden beiden Fällen auftreten:  
  
-   Als Projektionseigenschaft von "DbProjectExpression".  Bei dieser Verwendungsart gelten die folgenden Einschränkungen:  
  
    -   Der Ergebnistyp muss ein Zeilentyp sein.  
  
    -   Bei allen Argumenten handelt es sich um einen Ausdruck, der ein Ergebnis mit einem primitiven Typ erzeugt. In der Regel handelt es sich bei allen Argumenten um Skalarausdrücke, wie z. B. ein "PropertyExpression" über einem "DbVariableReferenceExpression", ein Funktionsaufruf oder eine arithmetische Berechnung von "DbPropertyExpression" über einem "DbVariableReferenceExpression" oder über einem Funktionsaufruf. In der Liste der Argumente für einen "DbNewInstanceExpression" können jedoch auch Ausdrücke auftreten, bei denen es sich um skalare Unterabfragen handelt. Bei einem Ausdruck, der einer skalaren Unterabfrage entspricht, handelt es sich um eine Ausdrucksstruktur, die einer Unterabfrage entspricht, die genau eine Zeile und eine Spalte eines primitiven Typs mit einem "DbElementExperession"-Objektstamm zurückgibt  
  
-   Mit einem Auflistungsrückgabetyp. In diesem Fall wird eine neue Auflistung der als Argumente bereitgestellten Ausdrücke definiert.  
  
#### <a name="dbvariablereferenceexpression"></a>DbVariableReferenceExpression  
 Bei einem "DbVariableReferenceExpression" muss es sich um ein untergeordnetes Element des Knotens "DbPropertyExpression" handeln.  
  
#### <a name="dbgroupbyexpression"></a>DbGroupByExpression  
 Die Aggregateigenschaft eines "DbGroupByExpression" kann nur über Elemente des Typs "DbFunctionAggregate" verfügen. Es gibt keine anderen Aggregattypen.  
  
#### <a name="dblimitexpression"></a>DbLimitExpression  
 Bei der "Limit"-Eigenschaft kann es sich nur um einen "DbConstantExpression" oder einen "DbParameterReferenceExpression" handeln. Ab Version 3.5 von .NET Framework gilt für die "WithTies"-Eigenschaft immer der Wert "false".  
  
#### <a name="dbscanexpression"></a>DbScanExpression  
 Bei der Verwendung in Ausgabebefehlsstrukturen entspricht „DbScanExpression“ effektiv einer Tabellensuche, einer Sicht oder einer Speicherabfrage, die mit „EnitySetBase::Target“ dargestellt wird.  
  
 Wenn die Metadateneigenschaft "Defining Query" des Ziels nicht Null ist, es sich um eine Abfrage darstellt wird, wird der Text der Abfrage für die in dieser Metadateneigenschaft in der jeweiligen anbietersprache (oder Dialekten verarbeitet), wie in der Speicherschemadefinition angegeben bereitgestellt.  
  
 Andernfalls entspricht das Ziel einer Tabelle oder Sicht. Das Schemapräfix befindet sich entweder in der Metadateneigenschaft "Schema", wenn nicht null, ist sonst Name des Entitätencontainers.  Namen der Tabelle oder Sicht ist entweder der Metadateneigenschaft "Table", sofern diese nicht Null, andernfalls die Name-Eigenschaft der Entität Basis festgelegt.  
  
 All diese Eigenschaften beruhen auf der Definition des entsprechenden "EntitySet" in der Speicherschema-Definitionsdatei (SSDL).  
  
### <a name="using-primitive-types"></a>Verwenden primitiver Typen  
 Wenn in Ausgabebefehlsstrukturen auf primitive Typen verwiesen wird, erfolgt der Verweis in der Regel anhand der primitiven Typen des konzeptionellen Modells. Für bestimmte Ausdrücke benötigen die Anbieter jedoch den entsprechenden primitiven Speichertyp. Beispiele für solche Ausdrücke sind "DbCastExpression" und möglicherweise "DbNullExpression", sofern der Anbieter für den entsprechenden Typ NULL umwandeln muss. In solchen Fällen sollten Anbieter die Zuordnung zum Anbietertyp anhand der Art des primitiven Typs und dessen Facets vornehmen.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL-Generierung](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
