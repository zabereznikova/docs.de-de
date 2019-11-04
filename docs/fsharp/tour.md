---
title: Einführung in F#
description: Untersuchen Sie einige der wichtigsten Features der F# Programmiersprache in dieser Tour mit Codebeispielen.
ms.date: 11/06/2018
ms.openlocfilehash: cfea2827dcec65f9e3606e8528179029e1f2db84
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423807"
---
# <a name="tour-of-f"></a>Tour durch F\#

Der beste Weg, um zu F# erfahren, ist das Lesen F# und Schreiben von Code. In diesem Artikel werden einige der wichtigsten Funktionen der F# Sprache vorgestellt, und Sie erhalten einige Code Ausschnitte, die Sie auf Ihrem Computer ausführen können. Weitere Informationen zum Einrichten einer Entwicklungsumgebung finden Sie unter [Getting Started](get-started/index.md).

Es gibt zwei grundlegende Konzepte F#in: Funktionen und Typen.  In dieser Tour werden die Funktionen der Sprache hervorgehoben, die in diese beiden Konzepte einfließen.

## <a name="executing-the-code-online"></a>Online Ausführung des Codes

Wenn Sie auf Ihrem F# Computer nicht installiert haben, können Sie alle Beispiele in Ihrem Browser mit " [Try F# on Webassembly](https://tryfsharp.fsbolero.io/)" ausführen. Der-Wert ist ein Dialekt F# von, der direkt in Ihrem Browser ausgeführt wird. Um die Beispiele anzuzeigen, die in der repl befolgt werden, sehen Sie sich die **Beispiele > F# > Tour von** in der linken Menüleiste der ausführbaren repl an.

## <a name="functions-and-modules"></a>Funktionen und Module

Die wichtigsten Bestandteile eines beliebigen F# Programms sind ***Funktionen*** , die in ***Modulen***organisiert sind.  \- [Funktionen](./language-reference/functions/index.md) führen Eingaben aus, um Ausgaben zu liefern, und Sie sind unter [Modulen](./language-reference/modules.md)organisiert. Dies ist die primäre Art und Weise F#, in der Sie Dinge gruppieren.  Sie werden mithilfe der [`let` Bindung](./language-reference/functions/let-bindings.md)definiert, die der Funktion einen Namen gibt und deren Argumente definieren.

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

`let` Bindungen sind auch, wie Sie einen Wert an einen Namen binden, ähnlich wie eine Variable in anderen Sprachen.  `let` Bindungen sind standardmäßig ***unveränderlich*** . Dies bedeutet, dass ein Wert oder eine Funktion nicht direkt geändert werden kann, sobald ein Wert oder eine Funktion an einen Namen gebunden ist.  Dies steht im Gegensatz zu Variablen in anderen Sprachen, die ***änderbar***sind, was bedeutet, dass ihre Werte jederzeit geändert werden können.  Wenn Sie eine änderbare Bindung benötigen, können Sie `let mutable ...` Syntax verwenden.

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Zahlen, boolesche Werte und Zeichen folgen

Als .NET-Sprache unter F# stützt die gleichen zugrunde liegenden [primitiven Typen](language-reference/basic-types.md) , die in .net vorhanden sind.

Im folgenden wird erläutert, wie verschiedene numerische Typen F#in dargestellt werden:

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

Folgende boolesche Werte und die Durchführung der grundlegenden bedingten Logik werden wie folgt aussehen:

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

Und hier sehen Sie, wie die grundlegende [Zeichen](./language-reference/strings.md) folgen Manipulation aussieht:

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tupel

[Tupel](./language-reference/tuples.md) sind eine große Sache in F#.  Dabei handelt es sich um eine Gruppierung unbenannter, aber geordneter Werte, die als Werte selbst behandelt werden können.  Betrachten Sie Sie als Werte, die von anderen Werten aggregiert werden.  Sie haben viele Verwendungsmöglichkeiten, wie z. b. die bequeme Rückgabe von mehreren Werten aus einer Funktion oder das Gruppieren von Werten für einige Ad-hoc-Funktionen.

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

Ab F# 4,1 können Sie auch `struct` Tupel erstellen.  Diese arbeiten auch vollständig mit c# 7/Visual Basic 15 Tupeln zusammen, die ebenfalls `struct` Tupel sind:

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

Beachten Sie Folgendes: da `struct` Tupel Werttypen sind, können Sie nicht implizit in verweistupel konvertiert werden oder umgekehrt.  Sie müssen explizit zwischen einem Verweis-und strukturtupel konvertieren.

## <a name="pipelines-and-composition"></a>Pipelines und Komposition

Pipeoperatoren wie `|>` werden beim Verarbeiten von Daten in F#ausgiebig verwendet. Diese Operatoren sind Funktionen, mit denen Sie auf flexible Weise "Pipelines" von Funktionen erstellen können. Im folgenden Beispiel wird erläutert, wie Sie diese Operatoren nutzen können, um eine einfache Funktions Pipeline zu erstellen:

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

Im vorherigen Beispiel wurden viele Funktionen von F#genutzt, darunter Listen Verarbeitungsfunktionen, erstklassige Funktionen und [partielle Anwendungen](./language-reference/functions/index.md#partial-application-of-arguments). Obwohl ein tiefgreifendes Verständnis der einzelnen Konzepte in gewisser Weise erweitert werden kann, sollte klar sein, wie einfach Funktionen zum Verarbeiten von Daten bei der Erstellung von Pipelines verwendet werden können.

## <a name="lists-arrays-and-sequences"></a>Listen, Arrays und Sequenzen

Listen, Arrays und Sequenzen sind drei primäre Sammlungs Typen in der F# Kernbibliothek.

Listen sind geordnete, unveränderliche [Auflistungen](./language-reference/lists.md) von Elementen desselben Typs.  Dabei handelt es sich um einzeln verknüpfte Listen, was bedeutet, dass Sie für die Enumeration gedacht sind, aber eine schlechte Wahl für den zufälligen Zugriff und die Verkettung, wenn Sie groß sind.  Dies steht im Gegensatz zu Listen in anderen gängigen Sprachen, die in der Regel keine einzeln verknüpfte Liste zur Darstellung von Listen verwenden.

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

[Arrays](./language-reference/arrays.md) sind *änderbare* Auflistungen von Elementen desselben Typs mit fester Größe.  Sie unterstützen den schnellen zufälligen Zugriff von Elementen und sind schneller F# als Listen, da Sie nur zusammenhängende Speicherblöcke sind.

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

[Sequenzen](./language-reference/sequences.md) sind eine logische Reihe von Elementen, die alle denselben Typ haben.  Dabei handelt es sich um einen allgemeineren Typ als Listen und Arrays, der in einer beliebigen logischen Reihenfolge von Elementen angezeigt werden kann.  Sie stellen auch heraus, dass Sie ***träge***sein können, was bedeutet, dass Elemente nur dann berechnet werden können, wenn Sie benötigt werden.

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Rekursive Funktionen

Das Verarbeiten von Auflistungen oder Sequenzen von Elementen erfolgt in der F#Regel mit [Rekursion](./language-reference/functions/index.md#recursive-functions) in.  Obwohl F# die Unterstützung für Schleifen und imperative Programmierung bietet, wird die Rekursion bevorzugt, da es einfacher ist, Richtigkeit sicherzustellen.

> [!NOTE]
> Im folgenden Beispiel wird der Musterabgleich über den `match` Ausdruck verwendet.  Dieses grundlegende Konstrukt wird weiter unten in diesem Artikel behandelt.

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

F#bietet auch vollständige Unterstützung für die Optimierung des Endaufrufs. Dies ist eine Möglichkeit, rekursive Aufrufe so zu optimieren, dass Sie so schnell wie ein Schleifen Konstrukt sind.

## <a name="record-and-discriminated-union-types"></a>Datensatz und Unterscheidungs-Union-Typen

Datensatz-und Union-Typen sind zwei grundlegende Daten F# Typen, die im Code verwendet werden, und sind im Allgemeinen die F# beste Möglichkeit, um Daten in einem Programm darzustellen.  Obwohl dies den Klassen in anderen Sprachen ähnelt, besteht einer der Hauptunterschiede darin, dass Sie über strukturelle Gleichheits Semantik verfügen.  Dies bedeutet, dass Sie "nativ" vergleichbar sind und die Gleichheit unkompliziert ist. Überprüfen Sie, ob eine solche gleich der anderen ist.

[Datensätze](./language-reference/records.md) sind ein Aggregat benannter Werte mit optionalen Membern (z. b. Methoden).  Wenn Sie mit C# oder Java vertraut sind, sollten diese ähnlich wie POCOS oder POJOs aussehen, und zwar nur mit Struktur Gleichheit und weniger Zeremonien.

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

Ab F# 4,1 können Sie auch Datensätze als `struct`s darstellen.  Dies erfolgt mit dem `[<Struct>]`-Attribut:

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

Unterscheidungs- [Unions (DUs)](./language-reference/discriminated-unions.md) sind Werte, die eine Anzahl benannter Formulare oder Fälle sein könnten.  Daten, die im-Typ gespeichert werden, können einen von mehreren unterschiedlichen Werten aufweisen.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

Sie können auch die Unterscheidung nach *Groß-/Kleinschreibung*als Unterscheidungs-Unions verwenden, um die Domänen Modellierung über primitive Typen zu erleichtern  Häufig werden Zeichen folgen und andere primitive Typen verwendet, um etwas darzustellen, und erhalten daher eine bestimmte Bedeutung.  Wenn Sie jedoch nur die primitive Darstellung der Daten verwenden, kann dies dazu führen, dass fälschlicherweise ein falscher Wert zugewiesen wird.  Das darstellen der einzelnen Informationstypen als einzelne Union mit einem einzelnen Fall kann die Richtigkeit in diesem Szenario erzwingen.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

Wie im obigen Beispiel gezeigt, müssen Sie, um den zugrunde liegenden Wert in einer Unterscheidungs-Union mit einem einzelnen Fall zu erhalten, den Wert explizit entpacken.

Außerdem unterstützen Sie auch rekursive Definitionen, sodass Sie problemlos Strukturen und grundsätzlich rekursive Daten darstellen können.  So können Sie z. b. eine binäre Such Struktur mit `exists`-und `insert` Funktionen darstellen.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

Da es Ihnen ermöglicht, die rekursive Struktur der Struktur im-Datentyp darzustellen, ist das Arbeiten mit dieser rekursiven Struktur unkompliziert und gewährleistet die Richtigkeit.  Dies wird auch bei Musterabgleich unterstützt, wie unten dargestellt.

Darüber hinaus können Sie mit dem Attribut "`[<Struct>]`" als `struct`s darstellen:

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

Dabei sind jedoch zwei wichtige Punkte zu beachten:

1. Eine Struktur-du kann nicht rekursiv definiert werden.
2. Eine Struktur-du muss für jeden der Fälle eindeutige Namen aufweisen.

Wenn Sie die obigen Schritte nicht ausführen, führt dies zu einem Kompilierungsfehler.

## <a name="pattern-matching"></a>Musterabgleich

Der [Muster](./language-reference/pattern-matching.md) Abgleich F# ist das Sprach Feature, das die Richtigkeit F# für den Betrieb von Typen ermöglicht.  In den obigen Beispielen haben Sie wahrscheinlich eine gewisse `match x with ...` Syntax bemerkt.  Dieses Konstrukt ermöglicht dem Compiler das Verständnis der Form von Datentypen, damit Sie alle möglichen Fälle bei der Verwendung eines Datentyps über den sogenannten vollständigen Musterabgleich berücksichtigen können.  Dies ist äußerst leistungsstark für die Richtigkeit und kann geschickt verwendet werden, um zu überprüfen, was normalerweise für die Kompilierzeit von Bedeutung wäre.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

Vielleicht haben Sie bemerkt, dass das `_` Muster verwendet wird.  Dies wird als Platzhalter [Muster](./language-reference/pattern-matching.md#wildcard-pattern)bezeichnet. Dies ist eine Methode, die besagt, dass es sich nicht darum geht, was etwas ist.  Obwohl es praktisch ist, können Sie versehentlich einen vollständigen Musterabgleich umgehen und nicht mehr von der Kompilierung der Kompilierzeit profitieren, wenn Sie `_`nicht sorgfältig verwenden.  Dies wird am besten verwendet, wenn Sie bei einem Musterabgleich bestimmte Teile eines aufgesetzten Typs nicht interessieren oder wenn Sie alle sinnvollen Fälle in einem Muster Vergleichs Ausdruck aufgezählt haben.

[Aktive Muster](./language-reference/active-patterns.md) sind ein weiteres leistungsfähiges Konstrukt, das mit dem Muster Vergleich verwendet werden soll.  Sie ermöglichen es Ihnen, Eingabedaten in benutzerdefinierte Formulare zu partitionieren  Sie können auch parametrisiert werden, sodass die Partition als Funktion definiert werden kann.  Die Erweiterung des vorherigen Beispiels zur Unterstützung von aktiven Mustern sieht in etwa wie folgt aus:

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Optionale Typen

Ein Sonderfall von Unterscheidungs-Union-Typen ist der Optionstyp, der so nützlich ist, dass er Teil F# der Kernbibliothek ist.

[Der Optionstyp](./language-reference/options.md) ist ein Typ, der einen von zwei Fällen darstellt: einen Wert oder überhaupt nichts.  Sie wird in jedem Szenario verwendet, in dem ein Wert von einem bestimmten Vorgang abgeleitet werden kann oder nicht.  Dadurch werden Sie gezwungen, beide Fälle zu berücksichtigen, sodass es zu einem Kompilierzeit-und nicht zur Laufzeit-Problem wird.  Diese werden häufig in APIs verwendet, bei denen `null` stattdessen "Nothing" darstellt. Dadurch entfällt die Notwendigkeit, sich über `NullReferenceException` in vielen Fällen Gedanken zu machen.

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Maßeinheiten

Eine einzigartige Funktion F#des Typsystems ist die Möglichkeit, mit Maßeinheiten Kontext für numerische Literale bereitzustellen.

[Maßeinheiten](./language-reference/units-of-measure.md) ermöglichen das Zuordnen eines numerischen Typs zu einer Einheit, z. b. "Meter" und die Ausführung von Funktionen für Einheiten statt für numerische Literale.  Dadurch kann der Compiler überprüfen, ob die Typen von numerischen Literalen, die in einem bestimmten Kontext verwendet werden, sinnvoll sind. Dadurch werden Laufzeitfehler, die dieser Art von Arbeit zugeordnet sind, beseitigt.

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

Die F# Core-Bibliothek definiert viele SI-Einheiten Typen und Einheiten Konvertierungen.  Weitere Informationen finden Sie im Microsoft.FSharp.Data.UnitSystems.si- [Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Klassen und Schnittstellen

F#bietet auch vollständige Unterstützung für .NET-Klassen,- [Schnittstellen](./language-reference/interfaces.md), [abstrakte Klassen](./language-reference/abstract-classes.md), [Vererbung](./language-reference/inheritance.md)usw.

[Klassen](./language-reference/classes.md) sind Typen, die .NET-Objekte darstellen, die Eigenschaften, Methoden und Ereignisse als Member aufweisen [können.](./language-reference/members/index.md)

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

Das Definieren von generischen Klassen ist ebenfalls sehr unkompliziert.

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

Um eine Schnittstelle zu implementieren, können Sie entweder `interface ... with`-Syntax oder einen [Objekt Ausdruck](./language-reference/object-expressions.md)verwenden.

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Zu verwendende Typen

Das vorhanden sein von Klassen, Datensätzen, Unterscheidungs-Unions und Tupeln führt zu einer wichtigen Frage: welche sollten Sie verwenden?  Wie die meisten Elemente in der Lebensdauer hängt die Antwort von Ihren Umständen ab.

Tupel eignen sich hervorragend für die Rückgabe mehrerer Werte aus einer Funktion und die Verwendung eines Ad-hoc-Aggregats von Werten als Wert selbst.

Datensätze sind ein "schrittweise" aus Tupeln mit benannten Bezeichnungen und Unterstützung Optionaler Member.  Sie eignen sich hervorragend für eine Low-Ceremony-Darstellung der Daten während der Übertragung durch das Programm.  Da Sie Struktur Gleichheit aufweisen, können Sie mit dem Vergleich leicht verwendet werden.

Unterscheidungs-Unions haben viele Verwendungsmöglichkeiten, aber der Hauptvorteil besteht darin, Sie in Verbindung mit dem Musterabgleich zu verwenden, um alle möglichen "Formen" zu berücksichtigen, die eine Daten aufweisen kann.  

Klassen sind aus vielen Gründen sehr nützlich, z. b. Wenn Sie Informationen darstellen und diese Informationen auch an die Funktionalität binden müssen.  Als Faustregel gilt: Wenn Sie über Funktionen verfügen, die konzeptionell an einige Daten gebunden sind, ist die Verwendung von Klassen und den Prinzipien der objektorientierten Programmierung ein großer Vorteil.  Klassen sind auch der bevorzugte Datentyp beim interagieren mit C# und Visual Basic, da diese Sprachen Klassen für fast alles verwenden.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie nun einige der primären Features der Sprache kennen gelernt haben, sollten Sie Ihre ersten F# Programme schreiben können.  Weitere Informationen zum Einrichten der Entwicklungsumgebung und zum Schreiben von Code finden Sie unter [Getting Started](get-started/index.md) .

Wenn Sie mehr erfahren möchten, können Sie die nächsten Schritte ausführen, aber wir empfehlen Ihnen die [Einführung in F# die funktionale Programmierung in](./introduction-to-functional-programming/index.md) , um sich mit den grundlegenden Konzepten der funktionalen Programmierung vertraut zu machen.  Diese sind für das entwickeln robuster Programme in F#von entscheidender Bedeutung.

Sehen Sie sich auch die [ F# Sprachreferenz](./language-reference/index.md) an, um eine umfassende Sammlung von konzeptionellen Inhalten F#in anzuzeigen.
