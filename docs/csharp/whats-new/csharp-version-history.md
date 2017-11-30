---
title: Der Verlauf der c# - C#-Handbuch
description: Das Aussehen der Sprache wie in den ersten Produktversionen, und wie hat dies hat sich seit?
keywords: .NET c# .NET Core, Neuigkeiten C#-Verlauf
author: erikdietrich
ms.author: wiwagn
ms.date: 09/20/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 207c97c5dd7e04f815da61bff7f44393aea86222
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="the-history-of-c"></a>Der Verlauf von c# #

Wie das Aussehen der Sprache in der früheste Variationen? Und wie hat dies hat sich seit?

## <a name="c-version-10"></a>C#-Version 1.0

Wenn Sie zurückgehen und sehen, die C#-Version 1.0 viel wie Java gesucht. Als [Teil die angegebenen Entwurfsziele für ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), es "einfache, moderne, allgemeine Zweck objektorientierte Sprache." werden gesucht  Zum Zeitpunkt erreicht sieht Java es vorgesehen diese frühen Ziele beim Entwurf.

Wenn Sie wieder auf c# 1.0 jetzt ansehen, bevorzugen Sie jedoch würde sich ein wenig dizzy. Es fehlt die integrierten Async-Funktionen und einige der benutzerdefinierbaren Funktionen um Generika, die es dauern, bis gewährt. Der Tat fehlten es vollständig bei Generika.  Und [LINQ](../linq/index.md)? Nicht verfügbar, noch. Würde, die einige Jahre stammen ein.

C#-Version 1.0 der Funktionen, verglichen mit heutigen blanker gesucht. Selbst die ausführlichen Code schreiben würden gefunden werden. Jedoch noch, Sie müssen an einer Stelle zu starten. C#-Version 1.0 wurde einer arbeitsfähigen Alternative zu Java auf der Windows-Plattform.

## <a name="c-version-20"></a>C#-Version 2.0

Abzurufenden interessante starten Dinge. Werfen wir einen Blick auf einige wichtigen Funktionen von c# 2.0, 2005, zusammen mit Visual Studio 2005 freigegeben:

- [Generika](../programming-guide/generics/index.md)
- [Partial types (Partielle Typen)](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Anonyme Methoden](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Nullable-Typen](../programming-guide/nullable-types/index.md)
- [Iteratoren](../programming-guide/concepts/iterators.md)
- [Kovarianz und Kontravarianz](../programming-guide/concepts/covariance-contravariance/index.md)

C# als Sprache ziemlich generische objektorientiertes (OO) gestartet wurden, geändert in c#, Version 2.0, die in Eile sind. Sobald ihnen ihre Feet darunter zugewiesen waren, gab es sie nach einigen schwerwiegenden Entwickler Problembereiche. Und sie nach ihnen auf eine große Weise.

Mit Generika haben Sie Typen und Methoden, die für einen beliebigen Datentyp ausgeführt werden können und gleichzeitig die typsicherheit beibehalten. Für die Instanz, so, dass eine <xref:System.Collections.Generic.List%601> Ihnen ermöglicht, haben `List<string>` oder `List<int>` und Typ sichere Vorgänge für diese Zeichenfolgen oder Ganzzahlen ausführen, während Sie diese durchlaufen. Dies ist besser als das Erstellen von `ListInt` erben oder das Umwandeln von `Object` für jeden Vorgang.

C#-Version 2.0 geschaltet Iteratoren. Kurz gesagt, können Sie das Durchlaufen der Elemente in einem `List` (oder anderer Enumerable-Typen) mit einem `foreach` Schleife. Müssen dies als Teil der Sprache erstrangige erheblich verbessert die Lesbarkeit der Sprache und Personen Möglichkeit Grund zum Code.

Und noch, C#-Fortsetzung zu einem gewissen Grad aufholen mit Java wiedergeben. Java war bereits Versionen veröffentlicht, die Generika und Iteratoren enthalten. Aber, die bald als die Sprachen, die sich voneinander weiterentwickelt ändern würde.

## <a name="c-version-30"></a>C#-Version 3.0

C#-Version 3.0 stammt Ende 2007 zusammen mit Visual Studio 2008, obwohl die vollständige Boot von Sprachfunktionen tatsächlich mit den C#-Version 3.5 kommen würde. Diese Version markiert eine wesentliche Änderung im Zunahme von c#. Diese hergestellt c# als einer tatsächlich großartigen Programmiersprache Ihrer Wahl. Werfen wir einen Blick auf einige wichtigen Funktionen in dieser Version:

- [Automatisch implementierte Eigenschaften](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
- [Query expressions (Abfrageausdrücke)](../linq/query-expression-basics.md)
- [Lambda-Ausdruck](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [Ausdrucksbaumstrukturen](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [Erweiterungsmethoden](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)

Rückblickend scheinen viele dieser Funktionen unvermeidlich und untrennbar. Alle zusammenpassen strategisch. Sie wird im Allgemeinen betrachtet, dass C#-Version des killer-Funktion den Abfrageausdruck, auch bekannt als Language-Integrated Query (LINQ) wurde.

Eine Sicht vor-untersucht Ausdruck Tress, Lambda-Ausdrücke und anonyme Typen als Fundament für die LINQ erstellt wird. Jedoch in beiden Fällen c# 3.0 ein revolutionäres Konzept dargestellt. C# 3.0 begonnen hat die Ressourcenzugriffs zum Aktivieren von c# in einer hybriden objektorientierten / funktionale Sprache.

Insbesondere können jetzt im SQL-Format, deklarativer Abfragen zum Ausführen von Vorgängen für Auflistungen, unter anderem schreiben. Anstelle des Schreibens von einem `for` Schleife, um die Berechnung des Durchschnitts, der eine Liste mit ganzen Zahlen verwendet, Sie können Sie dies jetzt tun so weit als `list.Average()`. Die Kombination von Abfrageausdrücken und Erweiterungsmethoden macht es aussehen, als wären die Liste mit ganzen Zahlen viel flexibler Eigentümer hatte.

Zeit für die Personen zu wirklich zu verstehen und zu integrieren das Konzept gedauert, aber würden sie schrittweise. Und nun Jahre später Code präziser, einfache und funktionsfähig ist.

## <a name="c-version-40"></a>C#-Version 4.0

C#-Version 4.0 hätte schwierig werden oben auf den bahnbrechende Status der Version 3.0 Leben. Mit Version 3.0 mussten C#-Sprache fest, aus der Schatten von Java aus, und in der häufigen Verwendung sind verschoben. Die Sprache wurde schnell elegante gewinnt.

Die nächste Version einige interessanten neuen Funktionen eingeführt:

- [Dynamische Bindung](../language-reference/keywords/dynamic.md)
- [Mit dem Namen/optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Generische kovariante und kontravariante](../../standard/generics/covariance-and-contravariance.md)
- [Eingebettete Interop-Typen](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

Eingebettete Interoptypen überwinden einen Bereich mit den Bereitstellung. Generische Ko- und Kontravarianz bieten Ihnen mehr Möglichkeiten zum Verwenden von Generika, aber das erscheint ein wenig academic und wahrscheinlich wertvollsten vom Autor des Framework und der Bibliothek. Benannte und optionale Parameter können Sie viele methodenüberladungen beseitigen und Komfort bieten. Aber keine dieser Funktionen sind genau Paradigma ändern.

Die wichtigste Funktion wurde die Einführung der `dynamic` Schlüsselwort. Die `dynamic` -Schlüsselwort in C#-Version 4.0 die Möglichkeit, den Compiler zum Zeitpunkt der Kompilierung eingeben überschreiben eingeführt. Mit dem dynamischen Schlüsselwort, können Sie Konstrukte wie dynamisch typisierte Sprachen wie JavaScript erstellen. Sie erstellen eine `dynamic x = "a string"` und 6, fügen Sie dann verlassen, bis die Common Language Runtime, was, als Nächstes geschehen soll sortieren.

Dies bietet Ihnen das Potenzial für Fehler, sondern auch hervorragende Leistung innerhalb der Sprache.

## <a name="c-version-50"></a>C#-Version 5.0

C#-Version 5.0 wurde eine sehr fokussierte Version der Sprache aufgelistet. Nahezu alle den Aufwand für die jeweilige Version wurde in einer anderen bahnbrechende Sprachkonzept integriert.  Dies ist die Liste der Hauptfunktionen:

- [Asynchrone Member](../async.md)
- [Aufrufer-Informationsattribute](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

Der Aufrufer Info-Attribut können Sie problemlos Informationen über den Kontext abrufen in dem Sie ohne eine Unmenge von Reflektion Standardcode Abfragebeispiel ausführen. Es gibt viele Verwendungsmöglichkeiten in Diagnose und Protokollierungsaufgaben für.

Aber `async` und `await` sind die tatsächlichen Sterne dieser Version. Wenn diese Funktionen in 2012 veröffentlicht wurde, geändert c# das Spiel erneut durch baking Asynchronie in der Sprache ein erstklassiges Teilnehmer. Wenn Sie jemals mit langwierige Operationen und die Implementierung von Rückrufen des Webs behandelt haben, mochten Sie wahrscheinlich diese Sprachfunktion.

## <a name="c-version-60"></a>C#-Version 6.0

Mit Version 3.0 und 5.0 mussten c# einige beeindruckenden Funktionen in einer objektorientierte Sprache hinzugefügt. Mit Version 6.0 würde es auf diese Weise einer bestimmenden killer Funktion wechseln und stattdessen viele Features, die Benutzer in der Sprache begeistert freigeben. Hier sind einige von ihnen:

- [Statische Importe](../language-reference/keywords/using-static.md)
- [Ausnahmefilter](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [Eigenschaft-Initialisierer](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Ausdruck ohne Text-Elemente](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [NULL propagator](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [Zeichenfolgeninterpolierung](../language-reference/keywords/interpolated-strings.md)
- [Nameof-operator](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [Wörterbuch-Initialisierer](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md)

Jede dieser Funktionen ist vollkommen interessant. Aber wenn Sie vollständig mit denen betrachten, sehen Sie eine interessante Muster. In dieser Version entfernt C#-Sprache Textbaustein, Code mehr knappe und besser lesbar zu machen. Damit diese Sprachversion Lüfter sauberen und einfachen Code, ein großer Gewinn wurde.

Obwohl es sich nicht um eine herkömmliche Sprachfunktion in sich selbst ist, würden sie einen anderen Schritt zusammen mit dieser Version. Sie freigegeben [Roslyn-Compiler als Hintergrunddienst](https://github.com/dotnet/roslyn). Der C#-Compiler ist jetzt in c# geschrieben, und Sie verwenden den Compiler als Teil Ihrer Programmierung einschätzen.

## <a name="c-version-70"></a>C#-Version 7.0

Der aktuelle Hauptversion-ist c#, Version 7.0. Diese Version bietet einige evolutionärem und kalte Daten in die Vein von c# 6.0, ohne dass der Compiler als Dienst. Hier sind einige der neuen Funktionen:

- [Variablen](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [Tupel und deconstruction](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [Mustervergleich](./csharp-7.md#pattern-matching)
- [Local functions (Lokale Funktionen)](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [Erweiterte Ausdruck ohne Text-Elemente](./csharp-7.md#more-expression-bodied-members)
- [Ref "lokal" aus und gibt zurück](./csharp-7.md#ref-locals-and-returns)

Alle diese Features bieten tolle neue Funktionen für Entwickler und die Möglichkeit, sogar saubereren Code als je zuvor schreiben. Eine Markierung ist die Deklaration von Variablen für die Verwendung mit kondensierend der `out` Schlüsselwort und können von mehreren Rückgabewerten über Tupel.

Sondern c# wird jemals umfassenderen verwenden eingefügt. .NET Core ist jetzt alle Betriebssysteme abzielt und verfügt über die Augen fest, in der Cloud und auf Portabilität.  Dies belegt sicherlich Thoughts und die Uhrzeit, zusätzlich zu den stattfindende mit neuen Funktionen der Language-Designer.

_Artikel_ [ _ursprünglich veröffentlicht, im Blog NDepend_](https://blog.ndepend.com/c-versions-look-language-history/)_, werden Erik Dietrich und Patrick Smacchia._
