---
title: Einführung in .NET
description: Eine Einführung in einige der wichtigsten Features von .NET
author: cartermp
ms.author: wiwagn
ms.date: 05/22/2017
ms.technology: dotnet-standard
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
ms.openlocfilehash: f4cd2e47da236d276a42b972265ffd1a2fe27310
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160338"
---
# <a name="tour-of-net"></a>Einführung in .NET

.NET ist eine Entwicklungsplattform für allgemeine Zwecke. Sie bietet mehrere wichtige Features wie Unterstützung für verschiedene Programmiersprachen, asynchrone und gleichzeitige Programmiermodelle und native Interoperabilität. Dadurch wird auf unterschiedlichen Plattformen eine Vielzahl von Szenarios ermöglicht.

Dieser Artikel bietet eine Einführung in einige der wichtigsten Features von .NET. Im Thema [.NET-Architekturkomponenten](components.md) finden Sie Informationen zu den Bestandteilen der Architektur und deren Verwendung.

## <a name="how-to-run-the-code-samples"></a>Ausführen der Codebeispiele

Informationen zum Einrichten einer Entwicklungsumgebung zum Ausführen der Codebeispiele finden Sie im Thema [Erste Schritte](get-started.md). Kopieren Sie Codebeispiele auf dieser Seite, und fügen Sie sie zum Ausführen in Ihrer Umgebung ein.

## <a name="programming-languages"></a>Programmiersprachen

.NET unterstützt mehrere Programmiersprachen. Die .NET-Implementierungen implementieren die [Common Language Infrastructure (CLI)](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/), die unter anderem eine sprachunabhängige Runtime und Spracheninteroperabilität angibt. Dies bedeutet, dass Sie zum Erstellen von Apps und Diensten in .NET eine beliebige .NET-Sprache auswählen können.

Microsoft entwickelt und unterstützt aktiv drei .NET-Sprachen: C#, F# und Visual Basic.

* C# ist einfach, leistungsstark, typsicher und objektorientiert, behält aber gleichzeitig die Ausdruckskraft und Eleganz der C-Sprachen bei. Wer sich mit C und ähnlichen Sprachen auskennt, hat wenig Probleme bei der Verwendung von C#. Weitere Informationen zu C# finden Sie im [Leitfaden für C#](../csharp/index.yml).

* F# ist eine plattformübergreifende, funktionsorientierte Programmiersprache, die auch die herkömmliche und imperative Programmierung unterstützt. Weitere Informationen zu F# finden Sie im [Leitfaden für F#](../fsharp/index.yml).

* Visual Basic ist eine einfach zu erlernende Sprache, mit der Sie eine Vielzahl von Apps erstellen können, die in .NET ausgeführt werden. Von allen .NET-Sprachen gleicht die Syntax von Visual Basic der menschlichen Sprache am meisten. Dies erleichtert den Einstieg in die Softwareentwicklung.

## <a name="automatic-memory-management"></a>Automatische Speicherverwaltung

.NET verwendet [Garbage Collection (GC)](garbage-collection/index.md), um eine automatische Speicherverwaltung für Programme bereitzustellen. Der Garbage Collector arbeitet bei der Speicherverwaltung mit dem Prinzip der Verzögerung und gibt dem App-Durchsatz den Vorzug vor dem sofortigen Erfassen von Arbeitsspeicher. Weitere Informationen zur Garbage Collection in .NET finden Sie unter [Grundlagen der Garbage Collection (GC)](garbage-collection/fundamentals.md).

Die beiden folgenden Zeilen weisen Speicher zu:

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L1-L2)]

Es gibt kein entsprechendes Schlüsselwort zum Aufheben der Speicherzuweisung, da diese automatisch erfolgt, wenn der Garbage Collector während seiner geplanten Ausführung Arbeitsspeicher freigibt.

Der Garbage Collector ist nur einer der Dienste, die bei der Sicherstellung der *Speichersicherheit* helfen. Ein Programm ist speichersicher, wenn es nur auf belegten Speicherplatz zugreift. Beispielsweise stellt die Runtime sicher, dass eine App nicht auf belegten Arbeitsspeicher außerhalb des zulässigen Bereichs eines Arrays zugreift.

Im folgenden Beispiel löst die Runtime eine <xref:System.IndexOutOfRangeException>-Ausnahme aus, um Speichersicherheit zu erzwingen:

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L4-L5)]

## <a name="working-with-unmanaged-resources"></a>Arbeiten mit nicht verwalteten Ressourcen

Einige Objekte verweisen auf *nicht verwaltete Ressourcen*. Nicht verwaltete Ressourcen sind Ressourcen, die nicht automatisch von der .NET-Runtime verwaltet werden. Ein Dateihandle ist z.B. eine nicht verwaltete Ressource. Ein <xref:System.IO.FileStream>-Objekt ist ein verwaltetes Objekt, aber es verweist auf ein Dateihandle, das nicht verwaltet ist. Wenn Sie mit <xref:System.IO.FileStream> fertig sind, müssen Sie das Dateihandle freigeben.

In .NET implementieren Objekte, die auf nicht verwaltete Ressourcen verweisen, die <xref:System.IDisposable>-Schnittstelle. Wenn Sie mit dem Objekt fertig sind, können Sie die <xref:System.IDisposable.Dispose>-Methode des Objekts aufrufen, die für die Freigabe nicht verwalteter Ressourcen zuständig ist. .NET-Sprachen stellen wie im folgenden Beispiel gezeigt eine praktische [`using`-Anweisung](../csharp/language-reference/keywords/using.md) für solche Objekte bereit:

[!code-csharp[UnmanagedResources](../../samples/csharp/snippets/tour/UnmanagedResources.csx#L1-L6)]

Sobald der `using`-Block abgeschlossen ist, ruft die .NET-Runtime automatisch die <xref:System.IDisposable.Dispose>-Methode des `stream`-Objekts auf, die das Dateihandle freigibt. Die Runtime tut dies ebenfalls, wenn eine Ausnahme das Steuerelement dazu veranlasst, den Block zu verlassen.

Weitere Einzelheiten dazu finden Sie in folgenden Themen:

* Informationen zu C# finden Sie im Thema [using-Anweisung (C#-Referenz)](../csharp/language-reference/keywords/using-statement.md).
* Informationen zu F# finden Sie unter [Ressourcenverwaltung: Das Use-Schlüsselwort](../fsharp/language-reference/resource-management-the-use-keyword.md).
* Informationen zu Visual Basic finden Sie im Thema [Using-Anweisung (Visual Basic)](../visual-basic/language-reference/statements/using-statement.md).

## <a name="type-safety"></a>Typsicherheit

Ein Objekt ist eine Instanz eines bestimmten Typs. Die einzigen Vorgänge, die für ein bestimmtes Objekt zulässig sind, gehören zum Typ des Objekts. Ein `Dog`-Typ kann `Jump`- und `WagTail`-Methoden besitzen, aber keine `SumTotal`-Methode. Ein Programm ruft nur die Methoden auf, die zu einem bestimmten Typ gehören. Alle anderen Aufrufe führen entweder zu einem Kompilierzeitfehler oder einer Laufzeitausnahme (bei Verwendung von dynamischen Features oder `object`).

.NET-Sprachen sind objektorientiert und arbeiten mit Hierarchien aus Basisklassen und abgeleiteten Klassen. Die .NET-Runtime lässt nur Objektumwandlungen und -aufrufe zu, die der Objekthierarchie entsprechen. Denken Sie daran, dass jeder in einer .NET-Sprache definierte Typ vom <xref:System.Object>-Basistyp abgeleitet ist.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L19-L23)]

Mithilfe der Typsicherheit lässt sich auch eine Kapselung erzwingen, indem die Genauigkeit der Accessorschlüsselwörter garantiert wird. Accessorschlüsselwörter sind Artefakte, die den Zugriff auf Member eines bestimmten Typs durch anderen Code steuern. Diese werden üblicherweise für verschiedene Arten von Daten innerhalb eines Typs verwendet, mit denen das Verhalten des Typs verwaltet wird.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L3-L3)]

C#, Visual Basic und F# unterstützen einen lokalen *Typrückschluss*. Ein Typrückschluss bedeutet, dass der Compiler den Typ eines Ausdrucks auf der linken Seite aus dem Ausdruck auf der rechten Seite ableitet. Dies bedeutet nicht, dass die Typsicherheit verletzt oder außer Kraft gesetzt wird. Der resultierende Typ besitzt einen starken Typ mit allem, was dies impliziert. `dog` aus dem vorherigen Beispiel wird umgeschrieben, um einen Typrückschluss einzufügen. Der Rest des Beispiels bleibt unverändert:

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L28-L34)]

F# weist sogar noch weitergehende Funktionen für den Typrückschluss auf als der Typrückschluss innerhalb einer Methode wie in C# und Visual Basic. Weitere Informationen finden Sie unter [Typrückschluss](../fsharp/language-reference/type-inference.md).

## <a name="delegates-and-lambdas"></a>Delegaten und Lambdas

Ein Delegat wird durch eine Methodensignatur dargestellt. Jede Methode mit dieser Signatur kann dem Delegaten zugewiesen werden und wird ausgeführt, wenn der Delegat aufgerufen wird.

Delegaten ähneln C++-Funktionszeigern, sind aber typsicher. Sie stellen eine Art separater Methode innerhalb des CLR-Typsystems dar. Reguläre Methoden werden an eine Klasse angefügt und können nur über statische oder instanzaufrufende Konventionen direkt aufgerufen werden.

Delegaten werden in .NET häufig in Ereignishandlern, beim Definieren asynchroner Vorgänge und in Lambdaausdrücken verwendet, die einer der Eckpfeiler von LINQ sind. Weitere Informationen finden Sie im Thema [Delegaten und Lambdas](delegates-lambdas.md).

## <a name="generics"></a>Generics

Generics ermöglichen dem Programmierer, beim Entwerfen der Klassen einen *Typparameter* einzuführen, über den der Clientcode (die Benutzer des Typs) den genauen Typ angeben kann, der anstelle des Typparameters verwendet werden soll.

Generics wurden hinzugefügt, um Programmierer beim Implementieren generischer Datenstrukturen zu unterstützen. Vor ihrer Einführung musste ein Typ wie der Typ `List` mit Elementen vom Typ `object` arbeiten, damit er generisch ist. Dies hat zu verschiedenen Leistungs- und Semantikproblemen sowie zu möglichen kleinen Laufzeitfehlern geführt. Ein allgemeiner Laufzeitfehler besteht, wenn eine Datenstruktur beispielsweise sowohl Integerwerte als auch Zeichenfolgen enthält und eine <xref:System.InvalidCastException> bei der Verarbeitung der Member der Liste ausgelöst wird.

Das folgende Beispiel zeigt ein einfaches Programm, das unter Verwendung einer Instanz von <xref:System.Collections.Generic.List%601>-Typen ausgeführt wird:

[!code-csharp[GenericsShort](../../samples/csharp/snippets/tour/GenericsShort.csx)]

Weitere Informationen finden Sie im Thema [Generische Typen (Generics) – Übersicht](generics.md).

## <a name="async-programming"></a>Asynchrone Programmierung

Die asynchrone Programmierung ist ein erstklassiges Konzept in .NET und bietet Unterstützung für asynchrone Vorgänge in der Runtime, in den Frameworkbibliotheken und in den .NET-Sprachkonstrukten. Intern basiert sie auf Objekten (z.B. `Task`), die davon profitieren, dass das Betriebssystem E/A-gebundene Aufträge so effizient wie möglich ausführt.

Erste Informationen über die asynchrone Programmierung in .NET finden Sie im Thema [Async (Übersicht)](async.md).

## <a name="language-integrated-query-linq"></a>Sprachintegrierte Abfrage (Language-Integrated Query, LINQ)

LINQ ist ein Satz leistungsstarker Features für C# und Visual Basic, mit denen Sie einfachen, deklarativen Code für Datenvorgänge schreiben können. Die Daten können in vielfältiger Form vorliegen (als In-Memory-Objekte, in einer SQL-Datenbank oder in einem XML-Dokument), aber der LINQ-Code weicht in der Regel nicht für die verschiedenen Datenquellen ab.

Weitere Informationen sowie einige Beispiele finden Sie im Thema [LINQ (Language Integrated Query)](using-linq.md).

## <a name="native-interoperability"></a>Native Interoperabilität

Jedes Betriebssystem umfasst eine Anwendungsprogrammierschnittstelle (Application Programming Interface, API), die Systemdienste bereitstellt. In .NET gibt es verschiedene Möglichkeiten, diese APIs aufzurufen.

Die wichtigste Methode, um native Interoperabilität zu erreichen, erfolgt über einen Plattformaufruf oder „P/Invoke“, der auf Linux- und Windows-Plattformen unterstützt wird. Eine nur unter Windows verfügbare Methode zum Erreichen nativer Interoperabilität wird als „COM interop“ bezeichnet und zur Arbeit mit [COM-Komponenten](/cpp/atl/introduction-to-com) in verwaltetem Code verwendet. Die Methode basiert auf der P/Invoke-Infrastruktur, funktioniert jedoch etwas anders.

Der Großteil der Interoperabilitätsunterstützung von Mono (und damit auch von Xamarin) für Java und Objective-C ist gleich aufgebaut, verwendet also die gleichen Prinzipien.

Weitere Informationen zu nativer Interoperabilität finden Sie im Artikel [Native Interoperabilität](native-interop/index.md).

## <a name="unsafe-code"></a>Unsicherer Code

Je nach Sprachunterstützung können Sie mit der CLR auf nativen Speicher zugreifen und Zeigerarithmetik über `unsafe`-Code ausführen. Diese Vorgänge werden für bestimmte Algorithmen sowie für die Systeminteroperabilität benötigt. Unsicherer Code ist zwar leistungsstark, aber von seiner Verwendung wird abgeraten, sofern er nicht für die Interoperabilität mit System-APIs oder zur Implementierung des effizientesten Algorithmus erforderlich ist. Unsicherer Code wird in verschiedenen Umgebungen möglicherweise unterschiedlich ausgeführt und bietet weder die Vorteile des Garbage Collectors noch Typsicherheit. Es wird empfohlen, die Verwendung von unsicherem Code so weit wie möglich einzugrenzen und den Code sehr gründlich zu testen.

Das folgende Beispiel zeigt die geänderte Version der `ToString()`-Methode aus der `StringBuilder`-Klasse. Es veranschaulicht, wie sich durch Verwendung von `unsafe`-Code effizient ein Algorithmus implementieren lässt, indem Arbeitsspeicherblöcke direkt verschoben werden:

[!code-csharp[Unsafe](../../samples/csharp/snippets/tour/Unsafe.csx)]

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie sich für eine Einführung in die C#-Features interessieren, lesen Sie [Einführung in C#](../csharp/tour-of-csharp/index.md).

Wenn Sie sich für eine Einführung in die F#-Features interessieren, werfen Sie einen Blick auf die [Einführung in F#](../fsharp/tour.md).

Wenn Sie damit beginnen möchten, eigenen Code zu schreiben, lesen Sie [Erste Schritte](get-started.md).

Weitere Informationen zu wichtigen Komponenten von .NET finden Sie unter [.NET-Architekturkomponenten](components.md).
