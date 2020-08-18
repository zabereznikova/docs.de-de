---
title: 'Die Geschichte von C#: Leitfaden für C#'
description: Wie sah die Sprache in ihren ersten Versionen aus und wie hat sie sich seitdem verändert?
author: erikdietrich
ms.date: 04/08/2020
ms.openlocfilehash: b5c320e4c55803547fa44793a46e4a3da65bd0cb
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063470"
---
# <a name="the-history-of-c"></a>Die Geschichte von C\#

Dieser Artikel erläutert den Verlauf jeder Hauptversion der Sprache C#. Das C#-Team entwickelt und ergänzt immer neue und innovative Features. Informationen zu den Status von Programmiersprachenfunktionen, so auch Funktionen, die für zukünftige Versionen geplant sind, finden Sie im [dotnet/roslyn-Repository](https://github.com/dotnet/roslyn/blob/master/docs/Language%20Feature%20Status.md) auf GitHub.

> [!IMPORTANT]
> Für einige der Features nutzt die Sprache C# Typen und Methoden in einer Struktur, die in der C#-Spezifikation als *Standardbibliothek* bezeichnet wird. Die .NET-Plattform stellt diese Typen und Methoden in verschiedenen Paketen bereit. Ein Beispiel ist die Ausnahmeverarbeitung. Alle `throw`-Anweisungen oder -Ausdrücke werden überprüft, um sicherzustellen, dass das ausgelöste Objekt von <xref:System.Exception> abgeleitet ist. Auf ähnliche Weise wird jedes `catch` überprüft, um sicherzustellen, dass der abgefangen Typ von <xref:System.Exception> abgeleitet ist. Jede Version kann neue Anforderungen hinzufügen. Um die neuesten Sprachfunktionen in älteren Umgebungen verwenden zu können, müssen Sie vielleicht bestimmte Bibliotheken installieren. Diese Abhängigkeiten werden auf der jeweiligen Seite für eine spezifische Version dokumentiert. Sie können mehr über die [Beziehungen zwischen Sprache und Bibliothek](relationships-between-language-and-library.md) erfahren, um Hintergrundinformationen zu dieser Abhängigkeit zu erhalten.

Die C#-Buildtools berücksichtigen die neueste Hauptversion der Standardsprachversion. Zwischen den Hauptversionen kann es Nebenversionen geben, die in anderen Artikeln in diesem Abschnitt erläutert werden. Sie müssen [die Sprachversion des Compilers konfigurieren](../language-reference/configure-language-version.md) und die Version auswählen, um die neuesten Features in einer Punktversion zu verwenden. Seit C# 7.0 gab es drei Nebenversionen:

- [C# 7.3](csharp-7-3.md):
  - C# 7.3 steht ab [Visual Studio 2017 Version 15.7](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) und [.NET Core 2.1 SDK](../../core/whats-new/dotnet-core-2-1.md) zur Verfügung.
- [C# 7.2](csharp-7-2.md):
  - C# 7.2 steht ab [Visual Studio 2017 Version 15.5](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) und [.NET Core 2.0 SDK](../../core/whats-new/dotnet-core-2-0.md) zur Verfügung.
- [C# 7.1](csharp-7-1.md):
  - C# 7.1 steht ab [Visual Studio 2017 Version 15.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) und [.NET Core 2.0 SDK](../../core/whats-new/dotnet-core-2-0.md) zur Verfügung.

## <a name="c-version-10"></a>C# Version 1.0

Die mit Visual Studio .NET 2002 veröffentlichte C#-Version 1.0 ähnelte Java sehr stark. Als [Teil der vorgegebenen Entwurfsziele für ECMA](https://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html) sollte sie eine „einfache, moderne, objektorientierte Universalsprache sein“.  Zu diesem Zeitpunkt bedeuteten die Ähnlichkeiten mit Java, dass die frühen Entwurfsziele erreicht wurden.

Wenn Sie sich C# 1.0 jedoch heute ansehen, wird Ihnen schwindlig. Es fehlten die integrierten Async-Funktionen und einige der cleveren Funktionen bezüglich Generics, die heute als selbstverständlich betrachtet werden. In der Tat fehlten Generics vollständig.  Und was ist mit [LINQ](../linq/index.md)? War noch nicht verfügbar. Bis zum Erscheinen dieser Erweiterungen dauerte es noch einige Jahre.

Im Vergleich zu heute sieht C# Version 1.0 jedoch ziemlich minimalistisch aus. Man musste selbst ausführlichen Code schreiben. Irgendwo musste man jedoch anfangen. C# Version 1.0 war eine brauchbare Alternative zu Java auf der Windows-Plattform.

Die wichtigsten Features von C# 1.0 umfassten:

- [Klassen](../programming-guide/classes-and-structs/classes.md)
- [Strukturen](../language-reference/builtin-types/struct.md)
- [Schnittstellen](../programming-guide/interfaces/index.md)
- [Ereignisse](../events-overview.md)
- [Eigenschaften](../properties.md)
- [Delegaten](../delegates-overview.md)
- [Operatoren und Ausdrücke](../language-reference/operators/index.md)
- [Anweisungen](../programming-guide/statements-expressions-operators/statements.md)
- [Attribute](../programming-guide/concepts/attributes/index.md)

## <a name="c-version-12"></a>C# Version 1.2

C# Version 1.2 wird in Visual Studio. NET 2003 bereitgestellt. Sie enthielt einige kleine Verbesserungen der Sprache. Die wichtigste Änderung betrifft, ab dieser Version, den in einer `foreach`-Schleife namens <xref:System.IDisposable.Dispose%2A> generierten Code in <xref:System.Collections.IEnumerator>, wenn <xref:System.Collections.IEnumerator><xref:System.IDisposable> implementiert hat.

## <a name="c-version-20"></a>C# Version 2.0

Nun wird es langsam interessant. Werfen wir einen Blick auf einige wichtige Features von C# 2.0, die im Jahr 2005 zusammen mit Visual Studio 2005 veröffentlicht wurden:

- [Generics](../programming-guide/generics/index.md)
- [Partial types (Partielle Typen)](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Anonyme Methoden](../language-reference/operators/delegate-operator.md)
- [Auf NULL festlegbare Werttypen](../language-reference/builtin-types/nullable-value-types.md)
- [Iteratoren](../programming-guide/concepts/iterators.md)
- [Kovarianz und Kontravarianz](../programming-guide/concepts/covariance-contravariance/index.md)

Andere Features von C# 2.0 fügten vorhandenen Features Funktionen hinzu:

- Separate Getter- und Setter-Zugriffsfunktionen
- Konvertierung von Methodengruppen (Delegate)
- Statische Klassen
- Delegatrückschlüsse

C# mag als allgemein gehaltene, objektorientierte (OO) Sprache angefangen haben. Das änderte sich mit C# Version 2.0 jedoch schnell. Sobald man diese im Griff hatte, widmete man sich einigen ernsten Problemfeldern der Entwickler. Und zwar in bedeutungsvoller Art und Weise.

Mit Generics können Typen und Methoden für einen beliebigen Typ ausgeführt werden, und sie behalten dennoch ihre Typsicherheit bei. Wenn Sie zum Beispiel <xref:System.Collections.Generic.List%601> haben, können Sie `List<string>` oder `List<int>` verwenden und typsichere Vorgänge für diese Zeichenfolgen oder Ganzzahlen ausführen, während Sie sie durchlaufen. Die Verwendung von Generics ist besser als das Erstellen von `ListInt`, das für jeden Vorgang von `ArrayList` abgeleitet oder aus `Object` umgewandelt wird.

C# Version 2.0 brachte Iteratoren mit sich. Kurz gesagt können Sie mit Iteratoren alle Elemente in einem `List` (oder anderen Enumerable-Typen) mit einer `foreach`-Schleife untersuchen. Als erstklassiger Bestandteil der Sprache verbesserten Iteratoren die Lesbarkeit der Sprache und die Möglichkeiten zum Erörtern des Codes erheblich.

Trotzdem hinkte C# weiter ein wenig hinter Java her. Von Java gab es bereits Versionen mit Generics und Iteratoren. Das sollte sich jedoch bald ändern, da sich die Sprachen weiter voneinander weg entwickelten.

## <a name="c-version-30"></a>C# Version 3.0

C# Version 3.0 wurde Ende 2007 zusammen mit Visual Studio 2008 veröffentlicht. Der volle Umfang an Sprachfeatures kam tatsächlich jedoch erst mit .NET Framework Version 3.5. Diese Version markierte eine wesentliche Veränderung in der Entwicklung von C#. Sie etablierte C# als eine wirklich beachtliche Programmiersprache. Werfen wir einen Blick auf einige wichtige Features in dieser Version:

- [Automatisch implementierte Eigenschaften](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
- [Query expressions (Abfrageausdrücke)](../linq/query-expression-basics.md)
- [Lambda-Ausdrücke](../language-reference/operators/lambda-expressions.md)
- [Ausdrucksbaumstrukturen](../expression-trees.md)
- [Erweiterungsmethoden](../programming-guide/classes-and-structs/extension-methods.md)
- [Implizit typisierte lokale Variablen](../language-reference/keywords/var.md)
- [Partielle Methoden](../language-reference/keywords/partial-method.md)
- [Objekt- und Elementinitialisierer](../programming-guide/classes-and-structs/object-and-collection-initializers.md)

Rückblickend scheinen viele dieser Features unvermeidlich und untrennbar. Sie alle passen strategisch zusammen. Im Allgemeinen wird angenommen, dass das durchschlagende Feature dieser Version von C# der Abfrageausdruck war, auch bekannt als Language Integrated Query (LINQ).

Bei genauerem Hinsehen zeigt sich, dass Ausdrucksbaumstrukturen, Lambdaausdrücke und anonyme Typen die Grundlage waren, auf der LINQ konstruiert wurde. In jedem Fall stellte C# 3.0 ein revolutionäres Konzept dar. C# 3.0 hatte mit dem Schaffen der Grundlagen begonnen, um C# in eine hybride objektorientierte/funktionale Sprache zu verwandeln.

Konkret konnte man nun deklarative Abfragen im Stil von SQL schreiben, unter anderem um Vorgänge an Sammlungen durchzuführen. Anstatt eine `for`-Schleife zu schreiben, um den Durchschnitt einer Liste von ganzen Zahlen zu berechnen, konnte man dies nun einfach als `list.Average()` ausführen. Die Kombination aus Abfrageausdrücken und Erweiterungsmethoden ließ es jedoch so aussehen, als wäre die Liste der ganzen Zahlen sehr viel intelligenter geworden.

Es dauerte eine Weile, aber nach und nach verstanden die Menschen das Konzept wirklich und integrierten es. Und nun, Jahre später, ist der Code sehr viel präziser, einfacher und funktionaler.

## <a name="c-version-40"></a>C# Version 4.0

Die C#-Version 4.0, die mit Visual Studio 2010 veröffentlicht wurde, konnte nicht an den Erfolg der Version 3.0 anknüpfen. Mit Version 3.0 bewegte sich C# deutlich aus dem Schatten von Java heraus und gewann an Bedeutung. Die Sprache wurde schnell elegant.

Die nächste Version führte einige interessante neue Features ein:

- [Dynamische Bindung](../language-reference/builtin-types/reference-types.md)
- [Benannte/optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Generische Kovarianz und Kontravarianz](../../standard/generics/covariance-and-contravariance.md)
- [Eingebettete Interop-Typen](../../framework/interop/type-equivalence-and-embedded-interop-types.md)

Eingebettete Interop-Typen überwanden eine Schwierigkeit beim Entwickeln. Generische Kovarianz und Kontravarianz bieten Ihnen mehr Möglichkeiten zum Verwenden von Generics. Sie sind allerdings recht theoretisch und werden vermutlich von Framework- und Bibliotheksautoren am meisten geschätzt. Mit benannten und optionalen Parametern können Sie Methodenüberladungen eliminieren. Außerdem bieten sie Bequemlichkeit. Keines dieser Features war jedoch bahnbrechend.

Das wichtigste Feature war die Einführung des `dynamic`-Schlüsselworts. Das in C# Version 4.0 eingeführte `dynamic`-Schlüsselwort gibt die Möglichkeit zum Überschreiben des Compilers bei Eingabe zur Kompilierzeit. Durch die Verwendung des dynamischen Schlüsselworts können Sie Konstrukte schreiben, die dynamisch typisierten Sprachen wie JavaScript ähneln. Sie können ein `dynamic x = "a string"` erstellen und dann sechs hinzufügen, und überlassen Sie es der Runtime herauszufinden, was als Nächstes geschehen soll.

Die dynamische Bindung kann zu Fehlern führen, bietet aber gleichzeitig eine hohe Leistungsfähigkeit innerhalb der Sprache.

## <a name="c-version-50"></a>C# Version 5.0

In der C#-Version 5.0, die mit Visual Studio 2012 veröffentlicht wurde, lag der Fokus auf ganz bestimmten Sprachaspekten. Nahezu die gesamte Arbeit für diese Version war einem weiteren bahnbrechenden Sprachkonzept gewidmet: den Modellen `async` und `await` für die asynchrone Programmierung.  Hier ist die Liste der wichtigsten Features:

- [Asynchrone Member](../async.md)
- [Attribute „CallerInfo“](../language-reference/attributes/caller-information.md)

### <a name="see-also"></a>Siehe auch

- [Code Project: Caller Info Attributes in C# 5.0](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp) (Aufruferinformationsattribute in C# 5.0)

Mit dem Attribut „CallerInfo“ können Sie leicht Informationen über den Kontext erhalten, in dem Sie ausführen, ohne auf Dutzende Reflektionscodebausteine zurückzugreifen. Es gibt viele Verwendungsmöglichkeiten für Diagnose- und Protokollierungsaufgaben.

Die eigentlichen Stars dieser Version sind aber `async` und `await`. Als diese Features im Jahr 2012 herauskamen, veränderte C# noch einmal alles, indem Asynchronität als erstrangiger Bestandteil in die Sprache eingearbeitet wurde. Wenn Sie schon einmal mit langlaufenden Vorgängen und der Implementierung von Rückrufnetzen zu tun hatten, haben Sie dieses Sprachfeature vermutlich zu schätzen gelernt.

## <a name="c-version-60"></a>C# Version 6.0

Mit den Versionen 3.0 und 5.0 wurde C# um wichtige neue Features in einer objektorientierten Sprache erweitert. In Version 6.0, die mit Visual Studio 2015 veröffentlicht wurde, lag der Fokus nicht auf einem einzelnen Hauptfeature, sondern auf der Implementierung vieler kleiner Verbesserungen, die das Programmieren mit C# noch effizienter machten. Hier sind einige davon:

- [Statische Importe](./csharp-6.md#using-static)
- [Ausnahmefilter](./csharp-6.md#exception-filters)
- [Initialisierer für automatische Eigenschaften](./csharp-6.md#auto-property-initializers)
- [Ausdruckskörpermember](./csharp-6.md#expression-bodied-function-members)
- [Nullpropagator](./csharp-6.md#null-conditional-operators)
- [Zeichenfolgeninterpolation](./csharp-6.md#string-interpolation)
- [nameof-Operator](./csharp-6.md#the-nameof-expression)
- [Indexinitialisierer](csharp-6.md#extension-add-methods-in-collection-initializers)

Zu weiteren neuen Features gehören:

- „Await“ in Catch- und Finally-Blöcken
- Standardwerte für Getter-exklusive Eigenschaften

Jedes dieser Features ist auf seine eigene Weise interessant. Wenn Sie die Features jedoch zusammen betrachten, erkennen Sie ein interessantes Muster. In dieser Version von C# wurden Codebausteine eliminiert, um den Code knapper und besser lesbar zu machen. Für Anhänger von klarem, einfachem Code war diese Sprachversion ein großer Gewinn.

Neben dieser Version wurde noch etwas anderes gemacht, auch wenn es sich nicht um ein herkömmliches Sprachfeature handelt. Der Compiler [Roslyn wurde als Dienst veröffentlicht](https://github.com/dotnet/roslyn). Der C#-Compiler ist nun in C# geschrieben, und Sie können den Compiler als Teil Ihrer Programmierarbeiten verwenden.

## <a name="c-version-70"></a>C# Version 7.0

Die C#-Version 7.0 wurde mit Visual Studio 2017 veröffentlicht. Diese Version bietet einige evolutionäre und tolle Aspekte im Stil von C# 6.0, aber ohne den Compiler als Dienst. Hier sind einige der neuen Features:

- [Out-Variablen](./csharp-7.md#out-variables)
- [Tupel und Dekonstruktionen](./csharp-7.md#tuples)
- [Mustervergleich](./csharp-7.md#pattern-matching)
- [Local functions (Lokale Funktionen)](./csharp-7.md#local-functions)
- [Erweiterte Ausdruckskörpermember](./csharp-7.md#more-expression-bodied-members)
- [Lokale ref-Variablen und Rückgaben](./csharp-7.md#ref-locals-and-returns)

Weitere Features umfassten:

- [Verwerfen](./csharp-7.md#discards)
- [Binäre Literale und Zahlentrennzeichen](./csharp-7.md#numeric-literal-syntax-improvements)
- [Throw expressions (Throw-Ausdrücke)](./csharp-7.md#throw-expressions)

Alle diese Features bieten tolle neue Möglichkeiten für Entwickler und erlauben es, einen noch saubereren Code als je zuvor zu schreiben. Ein Highlight ist das Verdichten der Variablendeklaration zur Verwendung mit dem `out`-Schlüsselwort und indem die Rückgabe mehrerer Werte über Tupel erlaubt wird.

C# kommt auf einem immer breiteren Feld zum Einsatz. .NET Core zielt nun auf alle Betriebssysteme ab und konzentriert sich stark auf die Cloud und auf Portabilität.  Diese neuen Funktionen nehmen zusätzlich zum Entwickeln neuer Features sicherlich viel Arbeit und Zeit in Anspruch.

## <a name="c-version-71"></a>C#-Version 7.1

Die *Punktreleases* von C# wurden mit C# 7.1 eingeführt. Mit dieser Version wurde das Konfigurationselement zur [Auswahl der Sprachversion](../language-reference/configure-language-version.md), drei neue Sprachfeatures und neues Compilerverhalten hinzugefügt.

Die neuen Sprachfeatures in diesem Release umfassen:

- [`async` `Main`-Methode](./csharp-7-1.md#async-main)
  - Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.
- [`default`Literale Ausdrücke](./csharp-7-1.md#default-literal-expressions)
  - Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.
- [Abgeleitete Tupelelementnamen](./csharp-7-1.md#inferred-tuple-element-names)
  - Die Namen von Tupelelementen können in den meisten Fällen von der Initialisierung eines Tupels abgeleitet werden.
- [Musterabgleich für generische Typparameter](./csharp-7-1.md#pattern-matching-on-generic-type-parameters)
  - Sie können Musterabgleichsausdrücke für Variablen verwenden, deren Typ ein generischer Typparameter ist.

Außerdem verfügt der Compiler über die zwei Optionen `-refout` und `-refonly`, mit denen die [Generierung der Referenzassembly](./csharp-7-1.md#reference-assembly-generation) gesteuert wird.

## <a name="c-version-72"></a>C#-Version 7.2

Mit C# 7.2 wurden einige kleine Sprachfeatures hinzugefügt:

- [Techniken zum Schreiben von sicherem, effizientem Code](./csharp-7-2.md#safe-efficient-code-enhancements)
  - Eine Kombination aus Verbesserungen der Syntax, die das Arbeiten mit Werttypen mithilfe von Verweissemantik ermöglichen.
- [Nicht schließende benannte Argumente](./csharp-7-2.md#non-trailing-named-arguments)
  - Positionelle Argumente können auf benannte Argumente folgen.
- [Führende Unterstriche in numerischen Literalen](./csharp-7-2.md#leading-underscores-in-numeric-literals)
  - Numerische Literale dürfen jetzt führende Unterstriche vor aufgeführten Stellen aufweisen.
- [`private protected`-Zugriffsmodifizierer](./csharp-7-2.md#private-protected-access-modifier)
  - Der `private protected`-Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen innerhalb der gleichen Assembly.
- [Bedingte`ref` Ausdrücke](./csharp-7-2.md#conditional-ref-expressions)
  - Das Ergebnis eines bedingten Ausdrucks (`?:`) kann jetzt ein Verweis sein.

## <a name="c-version-73"></a>C#-Version 7.3

Es gibt zwei Hauptdesigns in der C# 7.3-Version. Ein Design bietet Features, die ermöglichen, dass sicherer Code so leistungsfähig ist wie unsicherer Code. Das zweite Design bietet inkrementelle Verbesserungen vorhandener Funktionen. Darüber hinaus wurden in diesem Release neue Compileroptionen hinzugefügt.

Die folgenden neuen Features unterstützen das Design der besseren Leistung für sicheren Code:

- [Sie können ohne Anpinnen auf fixierte Felder zugreifen.](csharp-7-3.md#indexing-fixed-fields-does-not-require-pinning)
- [Sie können lokale `ref`-Variablen neu zuweisen.](csharp-7-3.md#ref-local-variables-may-be-reassigned)
- [Sie können Initialisierer für `stackalloc`-Arrays verwenden.](csharp-7-3.md#stackalloc-arrays-support-initializers)
- [Sie können `fixed`-Anweisungen mit jedem Typ verwenden, der ein Muster unterstützt.](csharp-7-3.md#more-types-support-the-fixed-statement)
- [Sie können zusätzliche generische Einschränkungen verwenden.](csharp-7-3.md#enhanced-generic-constraints)

Die folgenden Verbesserungen wurden an vorhandenen Features vorgenommen:

- [Sie können `==` und `!=` mit Tupeltypen testen.](csharp-7-3.md#tuples-support--and-)
- [Sie können Ausdrucksvariablen an mehreren Standorten verwenden.](csharp-7-3.md#extend-expression-variables-in-initializers)
- [Sie können Attribute dem Unterstützungsfeld automatisch implementierter Eigenschaften anfügen.](csharp-7-3.md#attach-attributes-to-the-backing-fields-for-auto-implemented-properties)
- [Die Auflösung der Methode, wenn Argumente um `in` unterscheiden, wurde verbessert.](csharp-7-3.md#in-method-overload-resolution-tiebreaker)
- [Die Auflösung von Überladungen weist jetzt weniger mehrdeutige Fälle auf.](csharp-7-3.md#improved-overload-candidates)

Die neuen Compileroptionen lauten:

- [`-publicsign` zum Ermöglichen des Signierens von Assemblys durch Open-Source-Software.](csharp-7-3.md#public-or-open-source-signing)
- [`-pathmap` zum Bereitstellen einer Zuordnung für Quellverzeichnisse.](csharp-7-3.md#pathmap)

## <a name="c-version-80"></a>C#-Version 8.0

C# 8.0 ist das erste Hauptrelease von C#, das speziell auf .NET Core ausgerichtet ist. Einige Features nutzen neue CLR-Funktionen, während andere Bibliothekstypen nutzen, die nur in .NET Core hinzugefügt wurden. C# 8.0 fügt der Sprache C# die folgenden Features und Verbesserungen hinzu:

- [Readonly-Member](./csharp-8.md#readonly-members)
- [Standardschnittstellenmethoden](./csharp-8.md#default-interface-methods)
- [Verbesserungen am Musterabgleich](./csharp-8.md#more-patterns-in-more-places):
  - [switch-Ausdrücke](./csharp-8.md#switch-expressions)
  - [Eigenschaftsmuster](./csharp-8.md#property-patterns)
  - [Tupelmuster](./csharp-8.md#tuple-patterns)
  - [Positionsmuster](./csharp-8.md#positional-patterns)
- [using-Deklarationen](./csharp-8.md#using-declarations)
- [Statische lokale Funktionen](./csharp-8.md#static-local-functions)
- [Verwerfbare Referenzstrukturen](./csharp-8.md#disposable-ref-structs)
- [Nullwerte zulassende Verweistypen](../language-reference/builtin-types/nullable-reference-types.md)
- [Asynchrone Streams](./csharp-8.md#asynchronous-streams)
- [Indizes und Bereiche](./csharp-8.md#indices-and-ranges)
- [NULL-Coalescing-Zuweisung](./csharp-8.md#null-coalescing-assignment)
- [Nicht verwaltete konstruierte Typen](./csharp-8.md#unmanaged-constructed-types)
- [Stackalloc in geschachtelten Ausdrücken](./csharp-8.md#stackalloc-in-nested-expressions)
- [Erweiterung von interpolierten ausführlichen Zeichenfolgen](./csharp-8.md#enhancement-of-interpolated-verbatim-strings)

Standardschnittstellenmember erfordern Verbesserungen in der CLR (Common Language Runtime). Diese Features wurden in der CLR für .NET Core 3.0 hinzugefügt. Bereiche, Indizes und asynchrone Datenströme erfordern neue Typen in den .NET Core 3.0-Bibliotheken. Nullable-Verweistypen, die im Compiler implementiert sind, sind weitaus nützlicher, wenn Bibliotheken mit Anmerkungen versehen sind, um semantische Informationen zum NULL-Status von Argumenten und Rückgabewerten anzugeben. Diese Anmerkungen werden in den .NET Core-Bibliotheken hinzugefügt.

_Dieser Artikel wurde_ [_ursprünglich auf dem NDepend-Blog veröffentlicht_](https://blog.ndepend.com/c-versions-look-language-history/) _und uns freundlicherweise von Erik Dietrich und Patrick Smacchia zur Verfügung gestellt._
