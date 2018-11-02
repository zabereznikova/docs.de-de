---
title: Einführung in F#
description: Untersuchen Sie in dieser Tour mithilfe von Codebeispielen einige der wichtigsten Funktionen der Programmiersprache F#.
ms.date: 02/28/2018
ms.openlocfilehash: 7a512b5fead8de69f025e791b6086c60dbfc1b24
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "50235712"
---
# <a name="tour-of-f"></a>Einführung in F# #

Der beste Weg zum Kennenlernen von F# besteht darin, F#-Code zu lesen und zu schreiben.  Dieser Artikel bietet eine Tour durch einige der wichtigsten Funktionen der Programmiersprache F# und stellt einige Codebeispiele bereit, die Sie selbst ausführen können.  Weitere Informationen zum Einrichten einer Entwicklungsumgebung finden Sie unter [Erste Schritte](tutorials/getting-started/index.md).

Es gibt zwei primäre Konzepte in F#: Funktionen und Typen.   In dieser Tour werden Features der Sprache vorgestellt, die unter diese beiden Konzepte fallen.

## <a name="functions-and-modules"></a>Funktionen und Module

Die wesentlichen Bausteine eines F#-Programms sind ***Funktionen***, die in ***Modulen*** organisiert sind.  [Funktionen](language-reference/functions/index.md) arbeiten mit Eingaben, um Ausgaben zu erzeugen, und sie werden in [Modulen](language-reference/modules.md) organisiert – der primären Form der Gruppierung in F#.  Die Module werden mithilfe der [`let`-Bindung](language-reference/functions/let-bindings.md) definiert, die die Funktion benennt und ihre Argumente definiert.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` Bindungen sind auch an, wie Sie einen Wert in einen Namen, die einer Variablen in anderen Sprachen wie binden.  `let` Bindungen sind ***unveränderliche*** standardmäßig, d. h., sobald ein Wert oder eine Funktion in einen Namen gebunden wird ist, es nicht geändert werden kann ein direktes.  Dies steht im Gegensatz zu Variablen in anderen Sprachen, die ***änderbare***, d. h. deren Werte kann geändert werden zu einem beliebigen Zeitpunkt in der Zeit.  Wenn Sie eine Bindung des änderbare benötigen, können Sie `let mutable ...` Syntax.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Zahlen, Zeichenfolgen und boolesche Werte

Als eine .NET-Sprache unterstützt F# die gleichen zugrunde liegenden [primitiven Typen](language-reference/primitive-types.md).

So werden die verschiedenen numerischen Datentypen in F# dargestellt:

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

Und so sehen boolesche Werte und die grundlegende bedingte Logik aus:

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

Eine grundlegende Manipulation von [Zeichenfolgen](language-reference/strings.md) sieht wie folgt aus:

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tupel

[Tupel](language-reference/tuples.md) sind ein großes Thema in F#.  Bei Tupeln handelt sich um eine Gruppe von unbenannten, jedoch sortierten Werten, die als eigenständige Werte betrachten werden können.  Stellen Sie sich Werte vor, die aus anderen Werten aggregiert werden.  Sie können vielseitig eingesetzt werden, z.B. für ein bequemes Zurückgeben mehrerer Werte aus einer Funktion oder zur Vereinfachung in einer Ad-hoc-Gruppierung.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

Ab F# 4.1 können Sie auch `struct`-Tupel erstellen.  Diese bieten vollständige Interoperabilität mit Tupeln aus C# 7/Visual Basic 15, bei denen es sich ebenfalls um `struct`-Tupel handelt:

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

Folgendes muss jedoch beachtet werden: `struct`-Tupel sind keine Werttypen, deshalb können sie nicht implizit in Referenz-Tupel konvertiert werden oder umgekehrt.  Sie müssen eine explizite Konvertierung zwischen Referenz-Tupel und Struktur-Tupel durchführen.

## <a name="pipelines-and-composition"></a>Pipelines und Komposition

Übergeben Sie Operatoren wie z. B. `|>` werden häufig verwendet, bei der Verarbeitung von Daten in F#. Diese Operatoren sind Funktionen, die Sie zum Herstellen von "Pipelines" von Funktionen auf flexible Weise zu ermöglichen. Im folgenden Beispiel wird erläutert wie Sie diese Operatoren zum Erstellen einer einfachen funktionalen Pipeline nutzen können:

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

Im vorherigen Beispiel vorgenommen verwenden viele der Features von F#, einschließlich der Liste Verarbeitungsfunktionen, Funktionen, und [teilweise Anwendung](language-reference/functions/index.md#partial-application-of-arguments). Obwohl ein umfassendes Verständnis all dieser Konzepte einer weiterführenden Erläuterung bedarf, sollte klar geworden sein, wie einfach Funktionen beim Erstellen von Pipelines zum Verarbeiten von Daten verwendet werden können.

## <a name="lists-arrays-and-sequences"></a>Listen, Arrays und Sequenzen

Listen, Arrays und Sequenzen sind drei primäre Auflistungstypen in der F#-Kernbibliothek.

[Listet](language-reference/lists.md) geordnete, unveränderliche Auflistungen von Elementen des gleichen Typs.  Sie sind einfach verknüpften Listen, was bedeutet, dass sie für die Enumeration, aber eine schlechte Wahl für wahlfreien Zugriff und Verkettung vorgesehen sind, wenn sie groß sind.  Dies ist im Gegensatz zu Listen in andere beliebten Sprachen an, die zur Darstellung von Listen in der Regel keine einfach verknüpften Liste verwenden.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[Arrays](language-reference/arrays.md) sind feste Größe, *änderbare* Auflistungen von Elementen des gleichen Typs.  Diese schnellen, wahlfreien Zugriff von Elementen zu unterstützen, und sind schneller als F#-Listen, da sie nur zusammenhängende Speicherblöcke sind.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[Sequenzen](language-reference/sequences.md) eine logische Reihe von Elementen, alle vom selben Typ sind.  Dies sind es sich um einen allgemeineren Typ als Listen und Arrays, kann Ihre "View" in jeder logische Reihe von Elementen.  Auch herausstellen, da sie sein können ***lazy***, was bedeutet, dass die Elemente berechnet werden können, nur, wenn sie benötigt werden.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Rekursive Funktionen

Verarbeiten von Auflistungen oder Sequenzen von Elementen erfolgt in der Regel mit [Rekursion](language-reference/functions/index.md#recursive-functions) in F# erläutert werden.  Obwohl F#-Unterstützung für Schleifen und imperative Programmierung verfügt, ist die Rekursion bevorzugte, da sie einfacher sicherstellen der Korrektheit ist.

>[!NOTE]
Das folgende Beispiel verwendet den Musterabgleich über die `match` Ausdruck.  Diese grundlegenden Konstrukt wird weiter unten in diesem Artikel behandelt.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F# bietet außerdem vollständige Unterstützung für Tail aufrufen, Optimierung, dies ist eine Möglichkeit, rekursive Aufrufe optimieren, damit sie ebenso schnell als eine Schleifenkonstruktion sind.

## <a name="record-and-discriminated-union-types"></a>Datensatz- und Unterscheidungs-Union-Typen

Datensatz und Union-Typen werden zwei grundlegende Datentypen in F#-Code verwendet und sind im Allgemeinen die beste Möglichkeit, Daten in einem F#-Programm darstellen.  Auch wenn sie ähneln Klassen in anderen Sprachen dadurch, ist ihre primäre Unterschied, dass sie die strukturelle Gleichheitssemantik aufweisen.  Dies bedeutet, dass sie "nativ" vergleichbar und Gleichheit einfach ist: nur überprüfen, ob eine gleich dem anderem ist.

[Datensätze](language-reference/records.md) sind ein Aggregat benannter Werte, mit optionalen Elementen (z. B. Methoden).  Wenn Sie mit c# oder Java vertraut sind, sollten klicken Sie dann diese Poco-Klassen oder POJOs - ähnelt nur mit strukturelle Gleichheit und weniger Aufwand können.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

Ab F# 4.1, können Sie auch Datensätze darstellen `struct`s.  Dies erfolgt mit der `[<Struct>]` Attribut:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[Unterscheidungs-Unions (Verteilungseinheiten)](language-reference/discriminated-unions.md) sind Werte, die eine Reihe von benannten Formulare oder Fälle werden konnte.  In den Typ gespeicherte Daten können es sich um eine von mehreren unterschiedlichen Werten sein.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

Sie können auch die Verteilungseinheiten als *Einzelfall-Unterscheidungs-Unions*, um Unterstützung bei der domänenmodellierung über primitive Typen.  Oft durchläuft, Zeichenfolgen und anderen primitiven Typen werden verwendet, um etwas darstellen, und erhalten somit eine besondere Bedeutung.  Jedoch kann nur die primitiven Darstellung der Daten führen beim Zuweisen von versehentlich ein falscher Wert.  Jede Art von Informationen wie eine unterschiedliche Einzelfall-Union darstellt, kann Richtigkeit, die in diesem Szenario erzwingen.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

Wie im obige Beispiel wird veranschaulicht, um den zugrunde liegenden Wert in einen Einzelfall-Unterscheidungs-Union zu erhalten, müssen Sie explizit entpacken.

Darüber hinaus unterstützen Verteilungseinheiten auch Definitionen werden rekursive, sodass Sie problemlos die Strukturen und grundsätzlich rekursive Daten darstellen.  Beispielsweise sieht wie Sie einer binären Suchstruktur mit darstellen können `exists` und `insert` Funktionen.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Da Verteilungseinheiten die rekursive Struktur der Struktur in den Datentyp darstellen können, auf diese rekursive Struktur ist unkompliziert und garantiert auf Richtigkeit.  Es wird auch in einem Mustervergleich unterstützt, wie unten dargestellt.

Sie können darüber hinaus Verteilungseinheiten als darstellen `struct`mit der `[<Struct>]` Attribut:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

Es gibt jedoch zwei wichtige Aspekte zu bedenken, dabei:

1. Eine Struktur DU darf nicht rekursiv definiert sein.
2. Eine Struktur DU muss für jeden der Fälle einen eindeutige Namen haben.

Fehler bei den oben genannten folgen, führt zu einem Kompilierungsfehler.

## <a name="pattern-matching"></a>Musterabgleich

[Übereinstimmende Muster](language-reference/pattern-matching.md) ist die F#-Sprache-Funktion die Richtigkeit für Vorgänge für F#-Typen ermöglicht.  In den obigen Beispielen haben Sie wahrscheinlich bemerkt, dass einiges an `match x with ...` Syntax.  Dieses Konstrukt kann den Compiler, der verstehen kann, die "Form" Datentypen, um gezwungen, alle möglichen Fälle berücksichtigen, wenn ein Datentyp, durch was bekannt ist als vollständige Musterabgleich mit.  Dies ist unglaublich leistungsfähige auf Richtigkeit, und auf "heben", was normalerweise relevant Runtime in während der Kompilierung wäre clever verwendet werden kann.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

Sie können auch die Kurzform `function` Konstrukt für den Musterabgleich, das ist nützlich, wenn beim Schreiben von Funktionen auf, die Stellen verwenden [teilweise Anwendung](language-reference/functions/index.md#partial-application-of-arguments):

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L744-L762)]

Sie haben möglicherweise bemerkt wird die Verwendung von der `_` Muster.  Dies bezeichnet man als den [Platzhaltermuster](language-reference/pattern-matching.md#wildcard-pattern), dies ist eine Möglichkeit, mit dem Text "Keine Rolle, was etwas ist".  Zwar praktisch ist, können Sie versehentlich zu umgehen, vollständig Musterabgleich und nicht mehr während der Kompilierung Gebieten profitieren, wenn man sich mit nicht `_`.  Es wird am besten verwendet, wenn Sie bestimmte Teile eines zerlegten Typs nicht relevant ist wenn Muster Abgleich oder die letzte Klausel, wenn Sie alle sinnvolle Fälle in einem musterabgleichsausdruck aufgezählt haben.

[Aktive Muster](language-reference/active-patterns.md) ein anderes leistungsfähiges Konstrukt mit dem Mustervergleich verwendet werden.  Sie können zum Partitionieren der Eingabedaten in benutzerdefinierten Formulare, zerlegt wird sie an der Aufrufsite für Muster übereinstimmen.  Sie können auch parametrisiert werden und somit zur Definition der Partition als Funktion ermöglicht.  Erweitern im vorherige Beispiel zur Unterstützung von aktive Muster sieht etwa folgendermaßen aus:

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Optionale Typen

Ein Sonderfall des Unterscheidungs-Union-Typen ist der Typ, der eignet sich daher, dass es sich um einen Teil der F#-Kernbibliothek ist.

[Der Optionstyp](language-reference/options.md) ist ein Typ, der eine der beiden Fälle darstellt: ein Wert oder nichts überhaupt.  Sie wird in jedem Szenario verwendet, in dem ein Wert möglicherweise vorhanden oder kann nicht von einem bestimmten Vorgang führen.  Dies zwingt dann für beide Fälle, die ein Problem während der Kompilierung, anstatt ein Laufzeit-Problem somit berücksichtigen.  Diese werden häufig in APIs verwendet, in denen `null` wird verwendet, um "nichts" stattdessen darstellen und Sie somit kümmern müssen `NullReferenceException` in vielen Fällen.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Maßeinheiten

Eine einzigartige Funktion des F# Typsystem ist die Möglichkeit, den Kontext für numerische Literale durch Einheiten bereitzustellen.

[Maßeinheiten](language-reference/units-of-measure.md) ermöglichen Ihnen das Zuordnen eines numerischen Typs mit einer Einheit, z. B. Meter und haben Funktionen ausführen können Einheiten anstelle numerischer Literale.  Dies ermöglicht es den Compiler an, stellen Sie sicher, dass die Typen von numerischen Literalen übergebenen sinnvoll unter einem bestimmten Kontext, wodurch persistenzspeicherpunkte Laufzeitfehler zugeordnet, dass diese Art von Aufgaben.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

Die F#-Kernbibliothek definiert viele SI-Typen und einheitenkonvertierungen.  Weitere Informationen finden Sie die [Microsoft.FSharp.Data.UnitSystems.SI-Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Klassen und Schnittstellen

F# bietet außerdem vollständige Unterstützung für .NET-Klassen, [Schnittstellen](language-reference/interfaces.md), [abstrakte Klassen](language-reference/abstract-classes.md), [Vererbung](language-reference/inheritance.md)und so weiter.

[Klassen](language-reference/classes.md) sind Typen, die .NET Objekte darstellen. die Eigenschaften, Methoden und Ereignisse wie stehen die [Mitglieder](language-reference/members/index.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

Definieren von generischen Klassen ist auch sehr einfach.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

Um eine Schnittstelle zu implementieren, können Sie mithilfe einer `interface ... with` Syntax oder [Objektausdruck](language-reference/object-expressions.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Welche Typen sollen verwenden

Das Vorhandensein von Klassen, die Datensätze, die Unterscheidungs-Unions und Tupel führt, um eine wichtige Frage: Welche sollten Sie verwenden?  Wie fast alles im Leben hängt Ihre Situation die Antwort.

Tupel sind hervorragend für zurückgeben mehrerer Werte aus einer Funktion und ein Aggregat Ad-hoc-Werte als ein Wert selbst.

Datensätze sind eine "Step-up" von Tupeln, dass mit dem Namen, Beschriftungen und Unterstützung für optionale Member.  Sie eignen sich hervorragend für eine ungezwungene-Darstellung der Daten bei der Übertragung über das Programm.  Da sie auf Strukturgleichheit überprüft haben, sind sie Vergleich einfach zu verwenden.

Unterscheidungs-Unions sind vielseitig, aber die Kern-Benefit ist in der Lage, nutzen diese in Verbindung mit dem Mustervergleich berücksichtigen, die für alle möglichen "Formen", die eine Daten enthalten können.  

Klassen eignen sich hervorragend für eine Vielzahl von Gründen, z. B. Wenn Sie Informationen darstellen und mit denen Sie diese Informationen an Funktionalität auch verknüpfen müssen.  Als Faustregel gilt Wenn Sie Funktionen verfügen, die im Prinzip um einige Daten gebunden ist ist mithilfe von Klassen und die Prinzipien der objektorientierten Programmierung ein großer Vorteil.  Klassen sind auch der bevorzugte Datentyp bei der Interaktion mit c# und Visual Basic, als diese Sprachen Klassen für nahezu alle verwenden.

## <a name="next-steps"></a>Nächste Schritte

Nun, da Sie einige der wichtigsten Funktionen der Sprache gesehen haben, sollten Sie Ihre erste F#-Programme zu schreiben sein!  Sehen Sie sich [Einstieg](tutorials/getting-started/index.md) zu erfahren, wie Sie Ihre Entwicklungsumgebung einrichten, und Schreiben von Code.

Die nächsten Schritte für weitere können beliebig sein, aber es wird empfohlen [Einführung in die funktionale Programmierung in F# ](introduction-to-functional-programming/index.md) abzurufenden mit Core Konzepte der funktionalen Programmierung vertraut.  Dieser werden wichtige bei der Erstellung von robusten Programme in F#.

Darüber hinaus sehen Sie sich die [F#-Sprachreferenz](language-reference/index.md) eine umfangreiche Sammlung von konzeptionellen Inhalten in F# angezeigt.
