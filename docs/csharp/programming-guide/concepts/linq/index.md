---
title: Language-Integrated Query (LINQ) (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 02-02-2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 65e882db800d51c69f6f135b4d4529af0bc86653
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---

# <a name="language-integrated-query-linq"></a>Sprachintegrierte Abfrage (Language-Integrated Query, LINQ)

Language Integrated Query (LINQ) bezeichnet einen Satz Technologien, die auf der direkten Integration der Abfragefunktionen in die Sprache C# basieren. Abfragen von Daten werden gewöhnlich als einfache Zeichenfolgen ohne Typüberprüfung zur Kompilierzeit und ohne IntelliSense-Unterstützung ausgedrückt. Darüber hinaus müssen Sie für jede Art von Datenquelle eine andere Abfragesprache erlernen: SQL-Datenbanken, XML-Dokumente, verschiedene Webdienste usw. Bei LINQ ist eine Abfrage ein erstklassiges Sprachkonstrukt, genauso wie Klassen, Methoden oder Ereignisse.

Für einen Entwickler, der Abfragen schreibt, ist der sichtbarste „sprachintegrierte“ Teil von LINQ der Abfrageausdruck. Abfrageausdrücke werden in einer deklarativen *Abfragesyntax* geschrieben. Mit der Abfragesyntax können Sie mit minimalem Codeeinsatz Filter-, Sortier- und Gruppiervorgänge in Datenquellen ausführen. Sie verwenden die gleichen grundlegenden Abfrageausdrucksmuster, um Daten in SQL-Datenbanken, ADO. NET-Datasets, XML-Dokumenten und -Streams sowie .NET-Auflistungen abzufragen und zu transformieren.

Das folgende Beispiel zeigt den vollständigen Abfragevorgang. Der vollständige Vorgang umfasst die Erstellung einer Datenquelle, die Definition des Abfrageausdrucks und die Ausführung der Abfrage in einer `foreach`-Anweisung.

[!code-cs[csProgGuideLINQ#11](../../../../../samples/snippets/csharp/concepts/linq/index_1.cs)]

## <a name="query-expression-overview"></a>Übersicht über Abfrageausdrücke

-   Abfrageausdrücke können verwendet werden, um Daten aus einer beliebigen LINQ-fähigen Datenquelle abzufragen und zu transformieren. Mit einer einzigen Abfrage können z.B. Daten aus einer SQL-Datenbank abgerufen und ein XML-Stream als Ausgabe generiert werden.  
  
-   Die Arbeit mit Abfrageausdrücken ist einfach, da sie viele vertraute Konstrukte der Sprache C# verwenden.  
  
-   Alle Variablen in einem Abfrageausdruck sind stark typisiert, obwohl Sie den Typ in vielen Fällen nicht explizit angeben müssen, da der Compiler ihn ableiten kann. Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](type-relationships-in-linq-query-operations.md).  
  
-   Eine Abfrage wird erst ausgeführt, wenn Sie die Abfragevariable durchlaufen, z.B. in einer `foreach`-Anweisung. Weitere Informationen finden Sie unter [Einführung in LINQ-Abfragen](introduction-to-linq-queries.md).  
  
-   Zur Kompilierzeit werden Abfrageausdrücke gemäß den in der C#-Spezifikation festgelegten Regeln in Methodenaufrufe des Standardabfrageoperators konvertiert. Jede Abfrage, die mithilfe der Abfragesyntax ausgedrückt werden kann, kann auch mithilfe der Methodensyntax ausgedrückt werden. In den meisten Fällen ist aber die Abfragesyntax präziser und besser lesbar. Weitere Informationen finden Sie unter [Spezifikation für die Sprache C#](../../../language-reference/language-specification.md) und [Übersicht über Standardabfrageoperatoren](standard-query-operators-overview.md).  
  
-   Beim Schreiben von LINQ-Abfragen empfiehlt sich diese Faustregel: Verwenden Sie die Abfragesyntax, wann immer es möglich ist, und verwenden Sie die Methodensyntax nur, wenn es nötig ist. Zwischen den beiden Formen gibt es keine semantischen oder leistungsbezogenen Unterschiede. Abfrageausdrücke sind oft besser lesbar als die entsprechenden in der Methodensyntax geschriebenen Ausdrücke.  
  
-   Für einige Abfragevorgänge, wie z.B. <xref:System.Linq.Enumerable.Count%2A> oder <xref:System.Linq.Enumerable.Max%2A>, gibt es keine entsprechende Abfrageausdrucksklausel, daher müssen diese als Methodenaufruf ausgedrückt werden. Die Methodensyntax kann auf verschiedene Weise mit der Abfragesyntax kombiniert werden. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](query-syntax-and-method-syntax-in-linq.md).  
  
-   Abfrageausdrücke können in Ausdrucksbaumstrukturen oder Delegaten kompiliert werden, je nachdem, auf welchen Typ die Abfrage angewendet wird. <xref:System.Collections.Generic.IEnumerable%601>-Abfragen werden zu Delegaten kompiliert. <xref:System.Linq.IQueryable>- und <xref:System.Linq.IQueryable%601>-Abfragen werden zu Ausdrucksbaumstrukturen kompiliert. Weitere Informationen finden Sie unter [Ausdrucksbaumstrukturen](../../../expression-trees.md).  

## <a name="next-steps"></a>Nächste Schritte

Um mehr zu LINQ zu erfahren, machen Sie sich zunächst unter [Grundlagen zu Abfrageausdrücken](../../../linq/query-expression-basics.md) mit einigen grundlegenden Konzepten vertraut, und lesen Sie dann die Dokumentation für die LINQ-Technologie, die Sie interessiert:   
-   XML-Dokumente: [LINQ to XML](linq-to-xml.md)  
  
-   ADO.NET Entity Framework: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)  
  
-   .NET-Auflistungen, -Dateien, -Zeichenfolgen usw.: [LINQ to Objects](linq-to-objects.md)

Tiefer greifende Einblicke in LINQ im Allgemeinen erhalten Sie unter [LINQ in C#](../../../linq/linq-in-csharp.md).

Informationen zu den ersten Schritten mit LINQ in C# erhalten Sie im Tutorial [Arbeiten mit LINQ](../../../tutorials/working-with-linq.md).




