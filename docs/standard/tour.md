---
title: "Einführung in .NET"
description: "Eine Einführung in einige der wichtigsten Features der .NET-Plattform."
keywords: ".NET, .NET Core, Einführung, Programmiersprachen, unsicher, Speicherverwaltung, Typsicherheit, asynchron"
author: cartermp
ms.author: wiwagn
ms.date: 02/09/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
ms.translationtype: Machine Translation
ms.sourcegitcommit: d00f2096e0799107a8a2ff1d12274c6026d4c27a
ms.openlocfilehash: 50e5b333f892cf469e9f3fe57a0325ac6d8e641f
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---

# Einführung in .NET
<a id="tour-of-net" class="xliff"></a>

.NET ist eine Entwicklungsplattform für allgemeine Zwecke.  Sie bietet mehrere wichtige Features, wie verschiedene Programmiersprachen, asynchrone und gleichzeitige Programmiermodelle und native Interoperabilität. Dadurch wird auf unterschiedlichen Plattformen eine Vielzahl von Szenarien ermöglicht.

Dieser Artikel bietet eine Einführung in einige der wichtigsten Features der .NET-Plattform.

Unter [.NET-Architekturkomponenten](components.md) finden Sie Informationen zu den einzelnen Bestandteilen der Architektur und deren Verwendung.

## Ausführen der Codebeispiele
<a id="how-to-run-the-code-samples" class="xliff"></a>

Informationen zum Einrichten einer Entwicklungsumgebung zum Ausführen der Codebeispiele finden Sie unter [Erste Schritte](get-started.md).  Sie können Codebeispiele auf dieser Seite kopieren und zum Ausführen in Ihrer Umgebung einfügen. 

> [!NOTE]
Zukünftig wird diese Dokumentationswebsite die Möglichkeit bieten, diese Codebeispiele in Ihrem Browser auszuführen.

## Programmiersprachen
<a id="programming-languages" class="xliff"></a>

.NET unterstützt mehrere Programmiersprachen.  .NET-Runtimes implementieren die [Common Language Infrastructure (CLI)](https://www.visualstudio.com/license-terms/ecma-c-common-language-infrastructure-standards/), die (unter anderem) eine sprachunabhängige Runtime und Spracheninteroperabilität angibt.  Dies bedeutet, dass Sie zum Erstellen von Apps und Diensten in .NET eine beliebige .NET-Sprache auswählen können.

Microsoft entwickelt und unterstützt aktiv drei .NET-Sprachen: C#, F# und Visual Basic .NET. 

* C# ist einfach, leistungsstark, typsicher und objektorientiert, behält aber gleichzeitig die Ausdruckskraft und Eleganz der C-Sprachen bei. Wer sich mit C und ähnlichen Sprachen auskennt, wird wenig Probleme bei der Verwendung von C# haben.  Weitere Informationen zu C# finden Sie im [Leitfaden für C#](../csharp/index.md).

* F# ist eine plattformübergreifende, funktionsorientierte Programmiersprache, die auch die herkömmliche und imperative Programmierung unterstützt.  Weitere Informationen zu F# finden Sie im [Leitfaden für F#](../fsharp/index.md).

* Visual Basic ist eine einfach zu erlernende Sprache, mit der Sie eine Vielzahl von Anwendungen erstellen können, die in .NET ausgeführt werden.

## Automatische Speicherverwaltung
<a id="automatic-memory-management" class="xliff"></a>

.NET verwendet [Garbage Collection](garbagecollection/index.md), um eine automatische Speicherverwaltung für Programme bereitzustellen.  Der Garbage Collector arbeitet bei der Speicherverwaltung mit dem Prinzip der Verzögerung und gibt dem Anwendungsdurchsatz den Vorzug vor dem sofortigen Erfassen von Arbeitsspeicher.  Weitere Informationen zur Garbage Collection in .NET finden Sie unter [Grundlagen der Garbage Collection (GC)](garbagecollection/fundamentals.md).

Die beiden folgenden Zeilen weisen Speicher zu:

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L1-L2)]

Es gibt kein entsprechendes Schlüsselwort zum Aufheben der Speicherzuweisung, da diese automatisch erfolgt, wenn der Garbage Collector während seiner geplanten Ausführung Arbeitsspeicher freigibt.

Der Garbage Collector ist nur einer der Dienste, die bei der Sicherstellung der *Speichersicherheit* helfen.  Das unveränderliche Merkmal der Speichersicherheit ist sehr einfach: Ein Programm ist speichersicher, wenn es nur auf Arbeitsspeicher zugreift, der zugewiesen (nicht freigegeben) wurde.  Die Laufzeit stellt z.B. sicher, dass Programme keine Indizierung über das Ende eines Arrays hinaus durchführen und nicht auf Phantomfelder hinter dem Ende eines Objekts zugreifen.

Im folgenden Beispiel löst die Laufzeit eine `InvalidIndexException`-Ausnahme aus, um Speichersicherheit zu erzwingen.

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L4-L5)]

## Arbeiten mit nicht verwalteten Ressourcen
<a id="working-with-unmanaged-resources" class="xliff"></a>

Einige Objekte verweisen auf *nicht verwaltete Ressourcen*. Nicht verwaltete Ressourcen sind Ressourcen, die nicht automatisch von der .NET-Laufzeit verwaltet werden.  Ein Dateihandle ist z.B. eine nicht verwaltete Ressource.  Ein @System.IO.FileStream -Objekt ist ein verwaltetes Objekt, aber es verweist auf ein Dateihandle, das nicht verwaltet ist.  Wenn Sie mit FileStream fertig sind, müssen Sie das Dateihandle freigeben.

In .NET implementieren Objekte, die auf nicht verwaltete Ressourcen verweisen, die @System.IDisposable -Schnittstelle.  Wenn Sie mit dem Objekt fertig sind, können Sie die @System.IDisposable.Dispose -Methode des Objekts aufrufen, die für die Freigabe nicht verwalteter Ressourcen zuständig ist.  .NET-Sprachen stellen eine praktische `using`-Syntax für solche Objekte bereit, so wie in folgendem Beispiel gezeigt:

[!code-csharp[UnmanagedResources](../../samples/csharp/snippets/tour/UnmanagedResources.csx#L1-L6)]

Sobald der `using`-Block abgeschlossen ist, ruft die .NET-Laufzeit automatisch die @System.IDisposable.Dispose -Methode des `stream`-Objekts auf, die das Dateihandle freigibt.  Die Laufzeit wird dies ebenfalls tun, wenn eine Ausnahme das Steuerelement dazu veranlasst, den Block zu verlassen.

Weitere Details finden Sie auf den folgenden Seiten:

* Für C#, [using-Anweisung](../csharp/language-reference/keywords/using-statement.md)
* Für F#, [Ressourcenverwaltung: Das `use`-Schlüsselwort](../fsharp/language-reference/resource-management-the-use-keyword.md)
* Für Visual Basic, [using-Anweisung](../visual-basic/language-reference/statements/using-statement.md)

## Typsicherheit
<a id="type-safety" class="xliff"></a>

Objekte werden in Form von Typen zugeordnet. Die einzigen Vorgänge, die für ein bestimmtes Objekt zulässig sind, und der Arbeitsspeicher, den dieses Objekt belegt, gehören zum Typ des Objekts. Ein `Dog`-Typ kann `Jump`- und `WagTail`-Methoden besitzen, wahrscheinlich aber keine `SumTotal`-Methode. Ein Programm kann nur die deklarierten Methoden eines bestimmten Typs aufrufen. Alle anderen Aufrufe führen entweder zu einem Fehler während der Kompilierung oder zu einer Laufzeitausnahme (bei Verwendung von dynamischen Features oder `object`).

.NET-Sprachen sind objektorientiert und arbeiten mit Hierarchien aus Basisklassen und abgeleiteten Klassen. Die .NET-Runtime lässt nur Objektumwandlungen und -aufrufe zu, die der Objekthierarchie entsprechen. Denken Sie daran, dass jeder in einer .NET-Sprache definierte Typ vom `object`-Basistyp abgeleitet ist.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L18-L23)]

Mithilfe der Typsicherheit lässt sich auch eine Kapselung erzwingen, indem die Genauigkeit der Accessorschlüsselwörter garantiert wird. Accessorschlüsselwörter sind Artefakte, die den Zugriff auf Member eines bestimmten Typs durch anderen Code steuern. Diese werden üblicherweise für verschiedene Arten von Daten innerhalb eines Typs verwendet, mit denen das Verhalten des Typs verwaltet wird.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L3-L3)]

C#, Visual Basic und F# unterstützen einen lokalen **Typrückschluss**. Typrückschluss bedeutet, dass der Compiler den Typ eines Ausdrucks auf der linken Seite aus dem Ausdruck auf der rechten Seite ableitet. Dies bedeutet nicht, dass die Typsicherheit verletzt oder außer Kraft gesetzt wird. Der resultierende Typ **besitzt** einen starken Typ mit allem, was dies impliziert. Wir schreiben die ersten beiden Zeilen des vorherigen Beispiels neu, um einen Typrückschluss einzuführen. Beachten Sie, dass der Rest des Beispiels vollständig gleich bleibt.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L28-L34)]

F# weist sogar noch weitergehende Funktionen für den Typrückschluss auf als den Typrückschluss innerhalb einer Methode wie in C# und Visual Basic.  Weitere Informationen finden Sie unter [Typrückschluss](../fsharp/language-reference/type-inference.md).

## Delegaten und Lambdas
<a id="delegates-and-lambdas" class="xliff"></a>

Delegaten ähneln C++-Funktionszeigern, mit dem großen Unterschied, dass sie typsicher sind. Sie stellen eine Art separater Methode innerhalb des CLR-Typsystems dar. Reguläre Methoden werden an eine Klasse angefügt und können nur über statische oder instanzaufrufende Konventionen direkt aufgerufen werden.

Delegaten werden in verschiedenen APIs und an anderen Stellen in der .NET-Welt verwendet, insbesondere über Lambdaausdrücke, die ein Kernstück von LINQ sind.

Weitere Informationen hierzu finden Sie im Dokument [Delegaten und Lambdas](delegates-lambdas.md).

## Generika
<a id="generics" class="xliff"></a>

Generika wurden in .NET Framework 2.0 ergänzt. Kurz gesagt: Generika ermöglichen dem Programmierer, beim Entwerfen der Klassen einen „Typparameter“ einzuführen, über den der Clientcode (die Benutzer des Typs) den genauen Typ angeben kann, der anstelle des Typparameters verwendet werden soll.

Generika wurden hinzugefügt, um Programmierer beim Implementieren generischer Datenstrukturen zu unterstützen. Vor der Einführung von Generika mussten Programmierer mit Elementen vom Typ `object` arbeiten, um z.B. den Typ `List` generisch zu machen. Das führte zu verschiedenen Probleme hinsichtlich der Leistung und der Semantik, von möglichen Laufzeitfehlern ganz zu schweigen. Die bekannteste Variante solcher Fehler tritt auf, wenn eine Datenstruktur z.B. sowohl ganze Zahlen als auch Zeichenfolgen enthält und beim Arbeiten mit den Members der Liste eine `InvalidCastException` ausgelöst wird.

Das folgende Beispiel zeigt ein einfaches Programm, das unter Verwendung einer Instanz von @System.Collections.Generic.List %601-Typen ausgeführt wird.

[!code-csharp[GenericsShort](../../samples/csharp/snippets/tour/GenericsShort.csx)]

Weitere Informationen finden Sie im Artikel [Generische Typen (Generika) – Übersicht](generics.md).

## Asynchrone Programmierung
<a id="async-programming" class="xliff"></a>

Die asynchrone Programmierung ist ein erstklassiges Konzept in .NET und bietet Unterstützung für asynchrone Vorgänge während der Laufzeit, in den Frameworkbibliotheken und in den .NET-Sprachkonstrukten. Intern basiert sie auf Objekten (z.B. `Task`), die davon profitieren, dass das Betriebssystem E/A-gebundene Jobs so effizient wie möglich ausführt.

Erste Informationen über die asynchrone Programmierung in .NET finden Sie unter [Async (Übersicht)](async.md).

## Sprachintegrierte Abfrage (Language-Integrated Query, LINQ)
<a id="language-integrated-query-linq" class="xliff"></a>

LINQ ist ein Satz leistungsstarker Features für C# und VB, mit denen Sie einfachen, deklarativen Code für Datenvorgänge schreiben können. Die Daten können in vielfältiger Form vorliegen (als In-Memory-Objekte, in einer SQL-Datenbank oder in einem XML-Dokument), aber der LINQ-Code unterscheidet sich in der Regel für die verschiedenen Datenquellen nicht.

Weitere Informationen sowie einige Beispiele finden Sie unter [LINQ (Language Integrated Query)](using-linq.md).

## Native Interoperabilität
<a id="native-interoperability" class="xliff"></a>

Jedes heute verwendete Betriebssystem stellt Plattformunterstützung für verschiedene Aufgaben der Programmierung bereit. .NET bietet verschiedene Möglichkeiten, diese APIs zu nutzen. Diese Unterstützung wird als „native Interoperabilität“ bezeichnet, und in diesem Abschnitt geht es darum, wie mit verwaltetem .NET-Code auf native APIs zugegriffen werden kann.

Die wichtigste Methode, um native Interoperabilität zu erreichen, erfolgt über einen Plattformaufruf: „P/Invoke“. Die Unterstützung in .NET Core steht für Linux- und Windows-Plattformen zur Verfügung. Eine andere, nur unter Windows verfügbare Methode zum Erreichen nativer Interoperabilität wird als „COM interop“ bezeichnet und zur Arbeit mit [COM-Komponenten](https://msdn.microsoft.com/library/bwa2bx93.aspx) in verwaltetem Code verwendet. Die Methode setzt auf der P/Invoke-Infrastruktur auf, funktioniert jedoch etwas anders.

Der Großteil der Interoperabilitätsunterstützung von Mono (und damit auch von Xamarin) für Java und Objective-C ist gleich aufgebaut, verwendet also die gleichen Prinzipien.

Weitere Informationen dazu finden Sie im Dokument [Native Interoperabilität](native-interop.md).

## Unsicherer Code
<a id="unsafe-code" class="xliff"></a>

Die CLR ermöglicht die Fähigkeit, über `unsafe`-Code auf nativen Arbeitsspeicher zuzugreifen und Zeigerarithmetik durchzuführen. Diese Vorgänge werden für bestimmte Algorithmen sowie für die Systeminteroperabilität benötigt. Unsicherer Code ist zwar leistungsstark, aber von seiner Verwendung wird abgeraten, sofern er nicht für die Interoperabilität mit System-APIs oder zur Implementierung des effizientesten Algorithmus erforderlich ist. Unsicherer Code wird in verschiedenen Umgebungen möglicherweise unterschiedlich ausgeführt und bietet auch nicht die Vorteile von Garbage Collector und Typsicherheit. Es wird empfohlen, die Verwendung von unsicherem Code so weit wie möglich eingrenzen und den Code sehr gründlich zu testen.

Das folgende Beispiel zeigt die geänderte Version der `ToString()`-Methode aus der `StringBuilder`-Klasse.  Es veranschaulicht, wie sich durch Verwendung von `unsafe`-Code effizient ein Algorithmus implementieren lässt, indem Arbeitsspeicherblöcke direkt verschoben werden:

[!code-csharp[Unsafe](../../samples/csharp/snippets/tour/Unsafe.csx)]

## Nächste Schritte
<a id="next-steps" class="xliff"></a>

Wenn Sie sich für eine Einführung in die C#-Features interessieren, lesen Sie [Einführung in C#](../csharp/tour-of-csharp/index.md).

Wenn Sie sich für eine Einführung in die F#-Features interessieren, lesen Sie [Einführung in F#](../fsharp/tour.md).

Wenn Sie damit beginnen möchten, eigenen Code zu schreiben, lesen Sie [Erste Schritte](get-started.md).

Weitere Informationen zu wichtigen Komponenten von .NET finden Sie unter [.NET-Architekturkomponenten](components.md).

