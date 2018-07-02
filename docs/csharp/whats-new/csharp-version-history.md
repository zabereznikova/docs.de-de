---
title: 'Die Geschichte von C#: Leitfaden für C#'
description: Wie sah die Sprache in ihren ersten Versionen aus und wie hat sie sich seitdem verändert?
author: erikdietrich
ms.date: 09/20/2017
ms.openlocfilehash: 3e3bf98d1435b237b2941758b8ed245baa970237
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207533"
---
# <a name="the-history-of-c"></a>Die Geschichte von C# #

Wie sah die Sprache in ihren ersten Versionen aus? Und wie hat sie sich im Laufe der Jahre verändert?

## <a name="c-version-10"></a>C# Version 1.0

Wenn Sie sich einmal die Version 1.0 von C# ansehen, werden Sie viele Gemeinsamkeiten mit Java feststellen. Als [Teil der vorgegebenen Entwurfsziele für ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html) sollte sie eine „einfache, moderne, objektorientierte Universalsprache sein“.  Zu diesem Zeitpunkt bedeuteten die Ähnlichkeiten mit Java, dass die frühen Entwurfsziele erreicht wurden.

Wenn Sie sich C# 1.0 jedoch heute ansehen, wird Ihnen schwindlig. Es fehlten die integrierten Async-Funktionen und einige der cleveren Funktionen bezüglich Generika, die heute als selbstverständlich betrachtet werden. In der Tat fehlten Generika vollständig.  Und was ist mit [LINQ](../linq/index.md)? War noch nicht verfügbar. Bis zum Erscheinen dieser Erweiterungen dauerte es noch einige Jahre.

Im Vergleich zu heute sieht C# Version 1.0 jedoch ziemlich minimalistisch aus. Man musste selbst ausführlichen Code schreiben. Irgendwo musste man jedoch anfangen. C# Version 1.0 war eine brauchbare Alternative zu Java auf der Windows-Plattform.

Die wichtigsten Features von C# 1.0 umfassten:

- [Klassen](../programming-guide/classes-and-structs/classes.md)
- [Strukturen](../programming-guide/classes-and-structs/structs.md)
- [Schnittstellen](../programming-guide/interfaces/index.md)
- [Ereignisse](../events-overview.md)
- [Eigenschaften](../properties.md)
- [Delegaten](../delegates-overview.md)
- [Ausdrücke](../programming-guide/statements-expressions-operators/expressions.md)
- [Anweisungen](../programming-guide/statements-expressions-operators/statements.md)
- [Attribute](../programming-guide/concepts/attributes/index.md)
- Literale

## <a name="c-version-20"></a>C# Version 2.0

Nun wird es langsam interessant. Werfen wir einen Blick auf einige wichtige Features von C# 2.0, die im Jahr 2005 zusammen mit Visual Studio 2005 veröffentlicht wurden:

- [Generika](../programming-guide/generics/index.md)
- [Partial types (Partielle Typen)](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Anonyme Methoden](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Nullable-Typen](../programming-guide/nullable-types/index.md)
- [Iteratoren](../programming-guide/concepts/iterators.md)
- [Kovarianz und Kontravarianz](../programming-guide/concepts/covariance-contravariance/index.md)

Andere Features von C# 2.0 fügten vorhandenen Features Funktionen hinzu:

- Separate Getter- und Setter-Zugriffsfunktionen
- Konvertierung von Methodengruppen (Delegate)
- Statische Klassen
- Delegatrückschlüsse

C# mag als allgemein gehaltene, objektorientierte (OO) Sprache angefangen haben. Das änderte sich mit C# Version 2.0 jedoch schnell. Sobald man diese im Griff hatte, widmete man sich einigen ernsten Problemfeldern der Entwickler. Und zwar in bedeutungsvoller Art und Weise.

Mit Generika können Typen und Methoden für einen beliebigen Typ ausgeführt werden, und sie behalten dennoch ihre Typsicherheit bei. Wenn Sie zum Beispiel <xref:System.Collections.Generic.List%601> haben, können Sie `List<string>` oder `List<int>` verwenden und typsichere Vorgänge für diese Zeichenfolgen oder Ganzzahlen ausführen, während Sie sie durchlaufen. Die Verwendung von Generika ist besser als das Erstellen von `ListInt`, das für jeden Vorgang von `ArrayList` abgeleitet oder aus `Object` umgewandelt wird.

C# Version 2.0 brachte Iteratoren mit sich. Kurz gesagt können Sie mit Iteratoren alle Elemente in einem `List` (oder anderen Enumerable-Typen) mit einer `foreach`-Schleife untersuchen. Als erstklassiger Bestandteil der Sprache verbesserten Iteratoren die Lesbarkeit der Sprache und die Möglichkeiten zum Erörtern des Codes erheblich.

Trotzdem hinkte C# weiter ein wenig hinter Java her. Von Java gab es bereits Versionen mit Generika und Iteratoren. Das sollte sich jedoch bald ändern, da sich die Sprachen weiter voneinander weg entwickelten.

## <a name="c-version-30"></a>C# Version 3.0

C# Version 3.0 wurde Ende 2007 zusammen mit Visual Studio 2008 veröffentlicht. Der volle Umfang an Sprachfeatures kam tatsächlich jedoch erst mit .NET Framework Version 3.5. Diese Version markierte eine wesentliche Veränderung in der Entwicklung von C#. Sie etablierte C# als eine wirklich beachtliche Programmiersprache. Werfen wir einen Blick auf einige wichtige Features in dieser Version:

- [Automatisch implementierte Eigenschaften](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
- [Query expressions (Abfrageausdrücke)](../linq/query-expression-basics.md)
- [Lambdaausdruck](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [Ausdrucksbaumstrukturen](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [Erweiterungsmethoden](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)
- [Implizit typisierte lokale Variablen](../language-reference/keywords/var.md)
- [Partielle Methoden](../language-reference/keywords/partial-method.md)
- Objekt- und Auflistungsinitialisierer

Rückblickend scheinen viele dieser Features unvermeidlich und untrennbar. Sie alle passen strategisch zusammen. Im Allgemeinen wird angenommen, dass das durchschlagende Feature dieser Version von C# der Abfrageausdruck war, auch bekannt als Language Integrated Query (LINQ).

Bei genauerem Hinsehen zeigt sich, dass Ausdrucksbaumstrukturen, Lambdaausdrücke und anonyme Typen die Grundlage waren, auf der LINQ konstruiert wurde. In jedem Fall stellte C# 3.0 ein revolutionäres Konzept dar. C# 3.0 hatte mit dem Schaffen der Grundlagen begonnen, um C# in eine hybride objektorientierte/funktionale Sprache zu verwandeln.

Konkret konnte man nun deklarative Abfragen im Stil von SQL schreiben, unter anderem um Vorgänge an Sammlungen durchzuführen. Anstatt eine `for`-Schleife zu schreiben, um den Durchschnitt einer Liste von ganzen Zahlen zu berechnen, konnte man dies nun einfach als `list.Average()` ausführen. Die Kombination aus Abfrageausdrücken und Erweiterungsmethoden ließ es jedoch so aussehen, als wäre die Liste der ganzen Zahlen sehr viel intelligenter geworden.

Es dauerte eine Weile, aber nach und nach verstanden die Menschen das Konzept wirklich und integrierten es. Und nun, Jahre später, ist der Code sehr viel präziser, einfacher und funktionaler.

## <a name="c-version-40"></a>C# Version 4.0

C#-Version 4.0 hatte es schwierig, an den bahnbrechenden Status von Version 3.0 anzuknüpfen. Mit Version 3.0 bewegte sich C# deutlich aus dem Schatten von Java heraus und gewann an Bedeutung. Die Sprache wurde schnell elegant.

Die nächste Version führte einige interessante neue Features ein:

- [Dynamische Bindung](../language-reference/keywords/dynamic.md)
- [Benannte/optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Generische Kovarianz und Kontravarianz](../../standard/generics/covariance-and-contravariance.md)
- [Eingebettete Interop-Typen](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

Eingebettete Interop-Typen überwanden eine Schwierigkeit beim Entwickeln. Generische Kovarianz und Kontravarianz bieten Ihnen mehr Möglichkeiten zum Verwenden von Generika. Sie sind allerdings recht theoretisch und werden vermutlich von Framework- und Bibliotheksautoren am meisten geschätzt. Mit benannten und optionalen Parametern können Sie Methodenüberladungen eliminieren. Außerdem bieten sie Bequemlichkeit. Keines dieser Features war jedoch bahnbrechend.

Das wichtigste Feature war die Einführung des `dynamic`-Schlüsselworts. Das in C# Version 4.0 eingeführte `dynamic`-Schlüsselwort gibt die Möglichkeit zum Überschreiben des Compilers bei Eingabe zur Kompilierzeit. Durch die Verwendung des dynamischen Schlüsselworts können Sie Konstrukte schreiben, die dynamisch typisierten Sprachen wie JavaScript ähneln. Sie können ein `dynamic x = "a string"` erstellen und dann sechs hinzufügen, und überlassen Sie es der Runtime herauszufinden, was als Nächstes geschehen soll.

Die dynamische Bindung kann zu Fehlern führen, aber gleichzeitig ermöglicht es hohe Leistung innerhalb der Sprache.

## <a name="c-version-50"></a>C# Version 5.0

C# Version 5.0 war eine fokussierte Version der Sprache. Beinahe die gesamten Mühen für diese Version flossen in ein weiteres bahnbrechendes Sprachkonzept: Die Modelle `async` und `await` für die asynchrone Programmierung.  Hier ist die Liste der wichtigsten Features:

- [Asynchrone Member](../async.md)
- [Attribute „CallerInfo“](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

Mit dem Attribut „CallerInfo“ können Sie leicht Informationen über den Kontext erhalten, in dem Sie ausführen, ohne auf Dutzende Reflektionscodebausteine zurückzugreifen. Es gibt viele Verwendungsmöglichkeiten für Diagnose- und Protokollierungsaufgaben.

Die eigentlichen Stars dieser Version sind aber `async` und `await`. Als diese Features im Jahr 2012 herauskamen, veränderte C# noch einmal alles, indem Asynchronität als erstrangiger Bestandteil in die Sprache eingearbeitet wurde. Wenn Sie schon einmal mit langlaufenden Vorgängen und der Implementierung von Rückrufnetzen zu tun hatten, haben Sie dieses Sprachfeature vermutlich zu schätzen gelernt.

## <a name="c-version-60"></a>C# Version 6.0

Mit den Versionen 3.0 und 5.0 wurde C# um wichtige neue Features in einer objektorientierten Sprache erweitert. Mit Version 6.0 brachte man nicht mehr ein dominantes, durchschlagendes Feature heraus, sondern stattdessen viele kleine Features, die die Produktivität beim Programmieren mit C# gesteigert haben. Hier sind einige davon:

- [Statische Importe](../language-reference/keywords/using-static.md)
- [Ausnahmefilter](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [Eigenschaftsinitialisierer](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Ausdruckskörpermember](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Nullpropagator](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md)
- [nameof-Operator](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [Indexinitialisierer](csharp-6.md#index-initializers)

Zu weiteren neuen Features gehören:

- „Await“ in Catch- und Finally-Blöcken
- Standardwerte für Getter-exklusive Eigenschaften

Jedes dieser Features ist auf seine eigene Weise interessant. Wenn Sie die Features jedoch zusammen betrachten, erkennen Sie ein interessantes Muster. In dieser Version von C# wurden Codebausteine eliminiert, um den Code knapper und besser lesbar zu machen. Für Anhänger von klarem, einfachem Code war diese Sprachversion ein großer Gewinn.

Neben dieser Version wurde noch etwas anderes gemacht, auch wenn es sich nicht um ein herkömmliches Sprachfeature handelt. Der Compiler [Roslyn wurde als Dienst veröffentlicht](https://github.com/dotnet/roslyn). Der C#-Compiler ist nun in C# geschrieben, und Sie können den Compiler als Teil Ihrer Programmierarbeiten verwenden.

## <a name="c-version-70"></a>C# Version 7.0

Die aktuellste Version ist C# 7.0. Diese Version bietet einige evolutionäre und tolle Aspekte im Stil von C# 6.0, aber ohne den Compiler als Dienst. Hier sind einige der neuen Features:

- [Out-Variablen](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [Tupel und Dekonstruktionen](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [Mustervergleich](./csharp-7.md#pattern-matching)
- [Local functions (Lokale Funktionen)](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [Erweiterte Ausdruckskörpermember](./csharp-7.md#more-expression-bodied-members)
- [Lokale ref-Variablen und Rückgaben](./csharp-7.md#ref-locals-and-returns)

Weitere Features umfassten:

- [Verwerfen](../discards.md)
- [Binary Literals (Binäre Literale)](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/binary-literals.md)
- [Digit Separators (Zahlentrennzeichen)](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/digit-separators.md)
- Ref-Rückgaben und lokale Variablen
- [Throw expressions (Throw-Ausdrücke)](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/throw-expression.md)

Alle diese Features bieten tolle neue Möglichkeiten für Entwickler und erlauben es, einen noch saubereren Code als je zuvor zu schreiben. Ein Highlight ist das Verdichten der Variablendeklaration zur Verwendung mit dem `out`-Schlüsselwort und indem die Rückgabe mehrerer Werte über Tupel erlaubt wird.

C# kommt auf einem immer breiteren Feld zum Einsatz. .NET Core zielt nun auf alle Betriebssysteme ab und konzentriert sich stark auf die Cloud und auf Portabilität.  Diese neuen Funktionen nehmen zusätzlich zum Entwickeln neuer Features sicherlich viel Arbeit und Zeit in Anspruch.

_Dieser Artikel_ wurde [_ursprünglich auf dem NDepend-Blog_](https://blog.ndepend.com/c-versions-look-language-history/) _veröffentlicht, mit freundlicher Genehmigung von Erik Dietrich und Patrick Smacchia._
