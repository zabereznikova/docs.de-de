---
title: "Form der Befehlsstrukturen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Form der Befehlsstrukturen
Das SQL\-Generierungsmodul generiert anhand eines angegebenen Eingabeabfragebefehlsstruktur\-Ausdrucks eine Back\-End\-spezifische SQL\-Abfrage.  In diesem Abschnitt werden die Merkmale, die Eigenschaften und die Struktur der Abfragebefehlsstrukturen erläutert.  
  
## Übersicht über die Abfragebefehlsstrukturen  
 Bei einer Abfragebefehlsstruktur handelt es sich um die Objektmodelldarstellung einer Abfrage.  Abfragebefehlsstrukturen dienen zwei Zwecken:  
  
-   Dem Ausdrücken einer Eingabeabfrage für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Dem Ausdrücken eine Ausgabeabfrage, die einem Anbieter übergeben wird und eine Back\-End\-Abfrage beschreibt.  
  
 Abfragebefehlsstrukturen unterstützen eine umfangreichere Semantik als SQL:1999\-kompatible Abfragen. Dies umfasst die Unterstützung von geschachtelten Auflistungen und Typvorgängen, z. B. bei der Prüfung, ob es sich bei einer Entität um einen bestimmten Typ handelt, oder beim Filtern von Sätzen anhand eines Typs.  
  
 Die "DBQueryCommandTree.Query"\-Eigenschaft ist der Stamm der Ausdrucksstruktur, die die Abfragelogik beschreibt.  Die "DBQueryCommandTree.Parameters"\-Eigenschaft enthält eine Liste der in der Abfrage verwendeten Parameter.  Die Ausdrucksstruktur besteht aus "DbExpression"\-Objekten.  
  
 Ein "DbExpression"\-Objekt stellt eine Berechnung dar.  Zum Verfassen von Abfrageausdrücken werden in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verschiedene Ausdrucksarten bereitgestellt, darunter Konstanten, Variablen, Funktionen, Konstruktoren und relationale Standardoperatoren, wie z. B. Filter und Join.  Alle "DbExpression"\-Objekte verfügen über eine ResultType\-Eigenschaft, die dem Typ des von diesem Ausdruck erzeugten Ergebnisses entspricht.  Dieser Typ wird als "TypeUsage" ausgedrückt.  
  
## Formen der Ausgabeabfrage\-Befehlsstruktur  
 Ausgabeabfrage\-Befehlsstrukturen entsprechen relationalen \(SQL\-\)Abfragen und unterliegen weitaus strengeren Regeln als Abfragebefehlsstrukturen.  In der Regel enthalten sie Konstrukte, die einfach in SQL übersetzt werden können.  
  
 Eingabebefehlsstrukturen werden für das konzeptionelle Modell ausgedrückt, das Navigationseigenschaften, Zuordnungen zwischen Entitäten und Vererbung unterstützt.  Ausgabebefehlsstrukturen werden für das Speichermodell ausgedrückt.  Mit Eingabebefehlsstrukturen können geschachtelte Auflistungen projiziert werden, nicht jedoch mit Ausgabebefehlsstrukturen.  
  
 Ausgabeabfrage\-Befehlsstrukturen beruhen auf einer Teilmenge der verfügbaren "DbExpression"\-Objekte. Selbst einige der Ausdrücke dieser Teilmenge unterliegen einer eingeschränkten Verwendung.  
  
 Typvorgänge, wie z. B. das Überprüfen, ob es sich bei einem angegebenen Ausdruck um einen bestimmten Typ handelt, oder das Filtern von Sätzen anhand eines Typs, sind in Ausgabebefehlsstrukturen nicht vorhanden.  
  
 In Ausgabebefehlsstrukturen werden für Projektionen nur Ausdrücke verwendet, die boolesche Werte zurückgeben. Dies gilt nur für Prädikate in Ausdrücken, die ein Prädikat, wie z. B. eine Filter\- oder eine Case\-Anweisung erfordern.  
  
 Der Stamm einer Ausgabeabfrage\-Befehlsstruktur ist ein "DbProjectExpression"\-Objekt.  
  
### Nicht in Ausgabeabfrage\-Befehlsstrukturen vorhandene Ausdrücke  
 Die folgenden Ausdruckstypen sind in einer Ausgabeabfrage\-Befehlsstruktur nicht gültig und müssen nicht von Anbietern behandelt werden:  
  
 DbDerefExpression  
  
 DbEntityRefExpression  
  
 DbRefKeyExpression  
  
 DbIsOfExpression  
  
 DbOfTypeExpression  
  
 DbRefExpression  
  
 DbRelationshipNavigationExpression  
  
 DbTreatExpression  
  
### Ausdruckseinschränkungen und Hinweise  
 Viele Ausdrücke können nur eingeschränkt in Ausgabeabfrage\-Befehlsstrukturen verwendet werden:  
  
#### DbFunctionExpression  
 Die folgenden Funktionstypen können übergeben werden:  
  
-   Kanonische Funktionen, die vom EDM\-Namespace erkannt werden.  
  
-   Integrierte \(Speicher\-\)Funktionen, die von "BuiltInAttribute" erkannt werden.  
  
-   Benutzerdefinierte Funktionen.  
  
 Kanonische Funktionen \(siehe [Kanonische Funktionen](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)\) werden als Teil von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] angegeben. Die Anbieter sollten anhand dieser Angaben Implementierungen für kanonische Funktionen bereitstellen.  Speicherfunktionen beruhen auf den Spezifikationen des entsprechenden Anbietermanifests.  Benutzerdefinierte Funktionen beruhen auf den SSDL\-Spezifikationen.  
  
 Zudem verfügen Funktionen mit dem "NiladicFunction"\-Attribut nicht über Argumente und sollten ohne die Klammer am Ende übersetzt werden.  D. h. zu *\<functionName\>* anstelle von *\<functionName\>\(\)*.  
  
#### DbNewInstanceExpression  
 "DbNewInstanceExpression" kann nur in den folgenden beiden Fällen auftreten:  
  
-   Als Projektionseigenschaft von "DbProjectExpression".  Bei dieser Verwendungsart gelten die folgenden Einschränkungen:  
  
    -   Der Ergebnistyp muss ein Zeilentyp sein.  
  
    -   Bei allen Argumenten handelt es sich um einen Ausdruck, der ein Ergebnis mit einem primitiven Typ erzeugt.  In der Regel handelt es sich bei allen Argumenten um Skalarausdrücke, wie z. B. ein "PropertyExpression" über einem "DbVariableReferenceExpression", ein Funktionsaufruf oder eine arithmetische Berechnung von "DbPropertyExpression" über einem "DbVariableReferenceExpression" oder über einem Funktionsaufruf.  In der Liste der Argumente für einen "DbNewInstanceExpression" können jedoch auch Ausdrücke auftreten, bei denen es sich um skalare Unterabfragen handelt.  Bei einem Ausdruck, der einer skalaren Unterabfrage entspricht, handelt es sich um eine Ausdrucksstruktur, die einer Unterabfrage entspricht, die genau eine Zeile und eine Spalte eines primitiven Typs mit einem "DbElementExperession"\-Objektstamm zurückgibt  
  
-   Mit einem Auflistungsrückgabetyp. In diesem Fall wird eine neue Auflistung der als Argumente bereitgestellten Ausdrücke definiert.  
  
#### DbVariableReferenceExpression  
 Bei einem "DbVariableReferenceExpression" muss es sich um ein untergeordnetes Element des Knotens "DbPropertyExpression" handeln.  
  
#### DbGroupByExpression  
 Die Aggregateigenschaft eines "DbGroupByExpression" kann nur über Elemente des Typs "DbFunctionAggregate" verfügen.  Es gibt keine anderen Aggregattypen.  
  
#### DbLimitExpression  
 Bei der "Limit"\-Eigenschaft kann es sich nur um einen "DbConstantExpression" oder einen "DbParameterReferenceExpression" handeln.  Ab Version 3.5 von .NET Framework gilt für die "WithTies"\-Eigenschaft immer der Wert "false".  
  
#### DbScanExpression  
 Bei der Verwendung in Ausgabebefehlsstrukturen entspricht "DbScanExpression" effektiv einer Tabellensuche, einer Sicht oder einer Speicherabfrage, die mit "EnitySetBase::Target" dargestellt wird.  
  
 Wenn die Metadateneigenschaft "Defining Query" des Ziels nicht NULL ist, dann entspricht sie einer Abfrage, deren Abfragetext in dieser Metadateneigenschaft in der jeweiligen Anbietersprache \(oder dem Dialekt\) bereitgestellt wird, wie in der Speicherschemadefinition angegeben.  
  
 Andernfalls entspricht das Ziel einer Tabelle oder Sicht.  Das Schemapräfix befindet sich entweder in der Metadateneigenschaft "Schema" \(sofern diese nicht NULL ist\), oder es handelt sich um den Entitätscontainernamen.  Beim Tabellen\- oder Sichtnamen handelt es sich entweder um die Metadateneigenschaft "Table" \(sofern diese nicht NULL ist\) oder um die "Name"\-Eigenschaft der Entitätenmengenbasis.  
  
 All diese Eigenschaften beruhen auf der Definition des entsprechenden "EntitySet" in der Speicherschema\-Definitionsdatei \(SSDL\).  
  
### Verwenden primitiver Typen  
 Wenn in Ausgabebefehlsstrukturen auf primitive Typen verwiesen wird, erfolgt der Verweis in der Regel anhand der primitiven Typen des konzeptionellen Modells.  Für bestimmte Ausdrücke benötigen die Anbieter jedoch den entsprechenden primitiven Speichertyp.  Beispiele für solche Ausdrücke sind "DbCastExpression" und möglicherweise "DbNullExpression", sofern der Anbieter für den entsprechenden Typ NULL umwandeln muss.  In solchen Fällen sollten Anbieter die Zuordnung zum Anbietertyp anhand der Art des primitiven Typs und dessen Facets vornehmen.  
  
## Siehe auch  
 [SQL\-Generierung](../../../../../docs/framework/data/adonet/ef/sql-generation.md)