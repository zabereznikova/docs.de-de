---
title: Language-Integrated Query (LINQ) (C#)
ms.date: 02/02/2017
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
ms.openlocfilehash: 07a9d68c042d524ee9faba8122b406a81e816378
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418239"
---
# <a name="language-integrated-query-linq"></a>Sprachintegrierte Abfrage (Language-Integrated Query, LINQ)

Language Integrated Query (LINQ) bezeichnet einen Satz Technologien, die auf der direkten Integration der Abfragefunktionen in die Sprache C# basieren. Abfragen von Daten werden gewöhnlich als einfache Zeichenfolgen ohne Typüberprüfung zur Kompilierzeit und ohne IntelliSense-Unterstützung ausgedrückt. Außerdem müssen Sie für jeden Datenquellentyp eine andere Abfragesprache lernen: SQL-Datenbanken, XML-Dokumente, verschiedene Webdienste usw. Bei LINQ ist eine Abfrage ein erstklassiges Sprachkonstrukt, genauso wie Klassen, Methoden oder Ereignisse. Sie schreiben Abfragen für stark typisierte Auflistungen von Objekten mithilfe von Sprachschlüsselwörtern und bekannten Operatoren. Die LINQ-Technologiefamilie bietet ein konsistentes Abfrageerlebnis für Objekte (LINQ to Objects), relationale Datenbanken (LINQ to SQL) und XML (LINQ to XML).

Für einen Entwickler, der Abfragen schreibt, ist der sichtbarste „sprachintegrierte“ Teil von LINQ der Abfrageausdruck. Abfrageausdrücke werden in einer deklarativen *Abfragesyntax* geschrieben. Mit der Abfragesyntax können Sie mit minimalem Codeeinsatz Filter-, Sortier- und Gruppiervorgänge in Datenquellen ausführen. Sie verwenden die gleichen grundlegenden Abfrageausdrucksmuster, um Daten in SQL-Datenbanken, ADO. NET-Datasets, XML-Dokumenten und -Streams sowie .NET-Auflistungen abzufragen und zu transformieren.

Sie können LINQ-Abfragen in C# für SQL Server-Datenbanken, XML-Dokumente, ADO.NET-Datasets und jede Auflistung von Objekten schreiben, die <xref:System.Collections.IEnumerable> oder die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützt. LINQ-Unterstützung wird auch von Drittanbietern für viele Webdienste und andere Datenbankimplementierungen bereitgestellt.

Das folgende Beispiel zeigt den vollständigen Abfragevorgang. Der vollständige Vorgang umfasst die Erstellung einer Datenquelle, die Definition des Abfrageausdrucks und die Ausführung der Abfrage in einer `foreach`-Anweisung.

[!code-csharp[csProgGuideLINQ#11](~/samples/snippets/csharp/concepts/linq/index_1.cs)]

Die folgende Abbildung aus Visual Studio zeigt eine teilweise abgeschlossene LINQ-Abfrage für eine SQL Server-Datenbank in C# und Visual Basic mit vollständiger Typüberprüfung und IntelliSense-Unterstützung:

![Diagramm einer LINQ-Abfrage mit IntelliSense](./media/introduction-to-linq/linq-query-intellisense.png)

## <a name="query-expression-overview"></a>Übersicht über Abfrageausdrücke

- Abfrageausdrücke können verwendet werden, um Daten aus einer beliebigen LINQ-fähigen Datenquelle abzufragen und zu transformieren. Mit einer einzigen Abfrage können z.B. Daten aus einer SQL-Datenbank abgerufen und ein XML-Stream als Ausgabe generiert werden.
- Die Arbeit mit Abfrageausdrücken ist einfach, da sie viele vertraute Konstrukte der Sprache C# verwenden.
- Alle Variablen in einem Abfrageausdruck sind stark typisiert, obwohl Sie den Typ in vielen Fällen nicht explizit angeben müssen, da der Compiler ihn ableiten kann. Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](type-relationships-in-linq-query-operations.md).
- Eine Abfrage wird erst ausgeführt, wenn Sie die Abfragevariable durchlaufen, z.B. in einer `foreach`-Anweisung. Weitere Informationen finden Sie unter [Einführung in LINQ-Abfragen](introduction-to-linq-queries.md).
- Zur Kompilierzeit werden Abfrageausdrücke gemäß den in der C#-Spezifikation festgelegten Regeln in Methodenaufrufe des Standardabfrageoperators konvertiert. Jede Abfrage, die mithilfe der Abfragesyntax ausgedrückt werden kann, kann auch mithilfe der Methodensyntax ausgedrückt werden. In den meisten Fällen ist aber die Abfragesyntax präziser und besser lesbar. Weitere Informationen finden Sie unter [Spezifikation für die Sprache C#](~/_csharplang/spec/expressions.md#query-expressions) und [Übersicht über Standardabfrageoperatoren](standard-query-operators-overview.md).
- Beim Schreiben von LINQ-Abfragen empfiehlt sich diese Faustregel: Verwenden Sie die Abfragesyntax, wann immer es möglich ist, und verwenden Sie die Methodensyntax nur, wenn es nötig ist. Zwischen den beiden Formen gibt es keine semantischen oder leistungsbezogenen Unterschiede. Abfrageausdrücke sind oft besser lesbar als die entsprechenden in der Methodensyntax geschriebenen Ausdrücke.
- Für einige Abfragevorgänge, wie z.B. <xref:System.Linq.Enumerable.Count%2A> oder <xref:System.Linq.Enumerable.Max%2A>, gibt es keine entsprechende Abfrageausdrucksklausel, daher müssen diese als Methodenaufruf ausgedrückt werden. Die Methodensyntax kann auf verschiedene Weise mit der Abfragesyntax kombiniert werden. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](query-syntax-and-method-syntax-in-linq.md).
- Abfrageausdrücke können in Ausdrucksbaumstrukturen oder Delegaten kompiliert werden, je nachdem, auf welchen Typ die Abfrage angewendet wird. <xref:System.Collections.Generic.IEnumerable%601>-Abfragen werden zu Delegaten kompiliert. <xref:System.Linq.IQueryable>- und <xref:System.Linq.IQueryable%601>-Abfragen werden zu Ausdrucksbaumstrukturen kompiliert. Weitere Informationen finden Sie unter [Ausdrucksbaumstrukturen](../../../expression-trees.md).

## <a name="next-steps"></a>Nächste Schritte

Um mehr zu LINQ zu erfahren, machen Sie sich zunächst unter [Grundlagen zu Abfrageausdrücken](../../../linq/query-expression-basics.md) mit einigen grundlegenden Konzepten vertraut, und lesen Sie dann die Dokumentation für die LINQ-Technologie, die Sie interessiert:

- XML-Dokumente: [LINQ to XML](linq-to-xml-overview.md)  
- ADO.NET Entity Framework: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)
- .NET-Collections, -Dateien, -Zeichenfolgen usw.: [LINQ to Objects](linq-to-objects.md)

Tiefer greifende Einblicke in LINQ im Allgemeinen erhalten Sie unter [LINQ in C#](../../../linq/linq-in-csharp.md).

Informationen zu den ersten Schritten mit LINQ in C# erhalten Sie im Tutorial [Arbeiten mit LINQ](../../../tutorials/working-with-linq.md).
