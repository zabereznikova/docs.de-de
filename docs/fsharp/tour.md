---
title: Überblick [F#]
description: Untersuchen Sie in dieser Tour mithilfe von Codebeispielen einige der wichtigsten Funktionen der Programmiersprache F#.
ms.date: 02/28/2018
ms.openlocfilehash: 2ce251b90d5c202996e0b1673e8f7f378a38af5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566284"
---
# <a name="tour-of-f"></a>Überblick [F#] #

Der beste Weg zum Kennenlernen von F# besteht darin, F#-Code zu lesen und zu schreiben.  Dieser Artikel bietet eine Tour durch einige der wichtigsten Funktionen der Programmiersprache F# und stellt einige Codebeispiele bereit, die Sie selbst ausführen können.  Weitere Informationen zum Einrichten einer Entwicklungsumgebung finden Sie unter [Erste Schritte](tutorials/getting-started/index.md).

Es gibt zwei primäre Konzepte in F#: Funktionen und Typen.  In dieser Tour werden Features der Sprache vorgestellt, die unter diese beiden Konzepte fallen.

## <a name="functions-and-modules"></a>Funktionen und Module

Die wesentlichen Bausteine eines F#-Programms sind ***Funktionen***, die in ***Modulen*** organisiert sind.  [Funktionen](language-reference/functions/index.md) arbeiten mit Eingaben, um Ausgaben zu erzeugen, und sie werden in [Modulen](language-reference/modules.md) organisiert – der primären Form der Gruppierung in F#.  Die Module werden mithilfe der [`let`-Bindung](language-reference/functions/let-bindings.md) definiert, die die Funktion benennt und ihre Argumente definiert.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` Bindungen sind auch an, wie Sie einen Wert an einen ähnlichen Namen, einer Variablen in anderen Sprachen wie binden.  `let` Bindungen sind ***unveränderlichen*** standardmäßig, d. h., sobald ein Wert oder eine Funktion mit einem Namen gebunden wird, es geändert werden kann direkte.  Dies steht im Gegensatz zu Variablen in anderen Sprachen, von denen sind ***änderbare***, d. h., deren Werte kann geändert werden zu einem beliebigen Zeitpunkt zeitlich.  Wenn Sie eine änderbare Bindung benötigen, können Sie `let mutable ...` Syntax.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Zahlen, boolesche Werte und Zeichenfolgen

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

Übergabeoperatoren (`|>`, `<|`, `||>`, `<||`, `|||>`, `<|||`) und zusammengesetzte Operatoren (`>>` und `<<`) werden bei der Verarbeitung von Daten in F# extensiv verwendet.  Diese Operatoren ermöglichen es Ihnen, in flexibler Weise "Pipelines" von Funktionen einzurichten.  Das folgende Beispiel zeigt, wie Sie diese Operatoren zum Erstellen einer einfachen funktionalen Pipeline nutzen können.

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L300)]

Im obigen Beispiel wurden viele Features von F# verwendet, darunter Funktionen zur Listenverarbeitung, Funktionen erster Klasse und die[teilweise Anwendung](language-reference/functions/index.md#partial-application-of-arguments).  Obwohl ein umfassendes Verständnis all dieser Konzepte einer weiterführenden Erläuterung bedarf, sollte klar geworden sein, wie einfach Funktionen beim Erstellen von Pipelines zum Verarbeiten von Daten verwendet werden können.

## <a name="lists-arrays-and-sequences"></a>Listen, Arrays und Sequenzen

Listen, Arrays und Sequenzen sind drei primäre Sammlungstypen in f#-Kernbibliothek.

[Listet](language-reference/lists.md) sind geordnete, unveränderliche Auflistungen von Elementen des gleichen Typs.  Sie sind einfach verknüpfte Listen, was bedeutet, dass sie für die Enumeration, aber eine schlechte Wahl für wahlfreien Zugriff und Verkettungen vorgesehen sind, sollten sie sich bei großen.  Diese im Gegensatz zu Listen in anderen gängigen Sprachen, die zur Darstellung von Listen in der Regel keine einfach verknüpfte Liste verwenden.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[Arrays](language-reference/arrays.md) fester Größe, werden *änderbare* Auflistungen von Elementen des gleichen Typs.  Sie unterstützt den schnellen zufälligen Zugriff von Elementen und sind schneller als ein F#-werden aufgeführt, da sie nur zusammenhängenden Speicherblöcke sind.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[Sequenzen](language-reference/sequences.md) sind eine logische Reihe von Elementen, alle den gleichen Typ aufweisen.  Hierbei handelt es sich um einen allgemeineren Typ als die "View" in jeder logische Reihe von Elementen, die Arrays und Listen.  Auch hervorzuheben, da sie stehen ***lazy***, was bedeutet, dass die Elemente berechnet werden können, nur, wenn sie benötigt werden.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Rekursive Funktionen

Verarbeiten von Auflistungen oder Elementsequenzen erfolgt in der Regel mit [Rekursion](language-reference/functions/index.md#recursive-functions) in F# erläutert werden.  Zwar f# unterstützt für Schleifen und imperativen Programmierung, ist Rekursion bevorzugte, da sie einfacher sicherstellen Richtigkeit ist.

>[!NOTE]
Das folgende Beispiel verwendet die Mustervergleich über die `match` Ausdruck.  Dieses grundlegende Konstrukt wird weiter unten in diesem Artikel behandelt.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F# bietet auch vollständige Unterstützung für Tail aufrufen Optimierung, dies ist eine Methode für die rekursive Aufrufe zu optimieren, sodass sie nur so schnell wie eine Schleifenkonstruktion sind.

## <a name="record-and-discriminated-union-types"></a>Datensatz- und diskriminierte Union-Typen

Datensatz und Union-Typen sind zwei grundlegende Datentypen, die in f#-Code verwendet und sind in der Regel die beste Möglichkeit zum Darstellen der Daten in einem f#-Programm.  Obwohl dadurch diese Klassen ähnlich wie in anderen Sprachen wird, ist eine der ihre wichtigsten Unterschiede Strukturgleichheit Semantik besitzen.  Dies bedeutet, dass sie "systemintern" vergleichbar sein, und auf Gleichheit einfach ist – nur überprüft, ob eine gleich dem anderem ist.

[Datensätze](language-reference/records.md) sind ein Aggregat benannter Werte, mit optionalen Elementen (z. B. Methoden).  Wenn Sie mit c# oder Java vertraut sind, sollte dann diese ähnlich POCOs oder POJOs - nur bei der strukturellen gleichheitsüberprüfung und weniger Zeremonie können.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

Ab f# 4.1, kann auch Datensätze gleichzeitig als repräsentieren `struct`s.  Dies erfolgt mit der `[<Struct>]` Attribut:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[Unterscheidungs-Unions (Verteilungseinheiten)](language-reference/discriminated-unions.md) sind Werte, die eine Anzahl von benannten Formulare oder Fälle werden konnte.  Geben Sie im gespeicherten Daten von mehreren unterschiedlichen Werten sind möglich.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

Sie können auch als Verteilungseinheiten *einzelnen Fall Unterscheidungs-Unions*, damit die mit der Domäne Modellieren von primitiven Typen.  Oft, Zeichenfolgen und anderen primitiven Typen werden verwendet, um etwas darstellen und werden daher eine bestimmte Bedeutung zugewiesen.  Allerdings kann nur die primitiven Darstellung der Daten dazu führen, Zuweisen von versehentlich ein falscher Wert!  Jede Art von Informationen wie eine unterschiedliche einzelnen Fall Union darstellt, kann Richtigkeit in diesem Szenario erzwingen.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

Wie im obigen Beispiel wird veranschaulicht, um den zugrunde liegenden Wert in einen einzelnen Fall Unterscheidungs-Union, zu erhalten, müssen Sie explizit entpacken.

Darüber hinaus unterstützen Verteilungseinheiten auch rekursive Definitionen, sodass Sie problemlos Strukturen als auch grundsätzlich rekursive Daten darzustellen.  Beispielsweise sieht wie Sie mit einer binären Suchstruktur darstellen können `exists` und `insert` Funktionen.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Da Verteilungseinheiten Sie zur Darstellung der rekursive Struktur der Struktur in den Datentyp ermöglichen, Vorgänge für diese rekursive Struktur ist einfach und Korrektheit gewährleistet.  Es wird auch in einem Mustervergleich müssen unterstützt, wie unten dargestellt.

Sie können darüber hinaus Verteilungseinheiten als darstellen `struct`s mit der `[<Struct>]` Attribut:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

Es gibt jedoch zwei wichtige Dinge zu bedenken, wenn dies zu erheblichen:

1. Eine Struktur DU kann nicht rekursiv definiert werden.
2. Eine Struktur DU muss eindeutige Namen für jeden der Fälle aufweisen.

Oben genannten Kriterien nicht einhalten, führt zu einem Kompilierungsfehler.

## <a name="pattern-matching"></a>Musterabgleich

[Übereinstimmende Muster](language-reference/pattern-matching.md) ist die F#-Sprache-Funktion die Richtigkeit für Vorgänge für f#-Typen ermöglicht.  In den obigen Beispielen werden Sie möglicherweise bemerkt, dass relativ viel `match x with ...` Syntax.  Dieses Konstrukt kann den Compiler, der weiß, die "Shape" Datentypen, zwingen Sie beim Verwenden eines Datentyp durch was bekannt ist als vollständig Mustervergleich aller möglichen Fälle berücksichtigt.  Dies ist äußerst leistungsfähigen auf Richtigkeit, und zum "lift", was normalerweise Besorgnis Runtime in Kompilierung wäre raffinierter verwendet werden kann.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L739)]

Sie können auch die Kurzform `function` Konstrukt, die für den Mustervergleich, nützlich, ist Wenn Sie schreiben gerade, Funktionen, die Stellen nutzen [teilweise Anwendung](language-reference/functions/index.md#partial-application-of-arguments):

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L741-L759)]

Etwas Ihnen möglicherweise aufgefallen ist die Verwendung von der `_` Muster.  Dies bezeichnet man die [Platzhaltermuster](language-reference/pattern-matching.md#wildcard-pattern), dies ist eine Möglichkeit, dies zu sagen "Ich kümmern sich nicht darum was etwas ist".  Obwohl es bequem erscheint, können Sie versehentlich umgehen vollständig Mustervergleich und nicht mehr vom Zeitpunkt der Kompilierung Erzwingungen profitieren, wenn Sie nicht mit Bedacht vorgehen `_`.  Es wird am besten verwendet, wenn Sie bestimmte Teile eines Typs zerlegten interessieren nicht wenn Muster entsprechen, oder der abschließenden Klausel, wenn Sie alle sinnvollen Fälle in einem Mustervergleichsausdruck aufgezählt haben.

[Aktive Muster](language-reference/active-patterns.md) anderes leistungsfähiges Instrument, mit dem Mustervergleich verwendet werden.  Dateien können Sie die Eingabedaten in benutzerdefinierte Formulare, Zerlegen von an der Aufrufsite für Muster Übereinstimmung zu partitionieren.  Sie können auch parametrisiert werden somit auf die Partition als Funktion definiert.  Erweitern im vorherige Beispiel zur Unterstützung von aktive Muster sieht ungefähr so aus:

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L761-L783)]

## <a name="optional-types"></a>Optionale Typen

Ein Sonderfall des Unterscheidungs-Union-Typen wird der Optionstyp der eignet sich daher, dass es ein Teil der f#-Kernbibliothek handelt.

[Der Optionstyp](language-reference/options.md) ist ein Typ, der eine der beiden Fälle darstellt: ein Wert oder nichts überhaupt.  Es wird in jedem Szenario verwendet, in dem ein Wert kann oder möglicherweise nicht von einem bestimmten Vorgang.  Dies erzwingt dann für beide Fälle Besorgnis Kompilierzeit statt Besorgnis Runtime somit berücksichtigen.  Diese werden häufig in APIs verwendet, in denen `null` wird verwendet, um "nichts" stattdessen darstellen somit Dadurch entfällt die Notwendigkeit kümmern `NullReferenceException` in vielen Fällen.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L791-L811)]

## <a name="units-of-measure"></a>Maßeinheiten

Eine einzigartige Funktion des # des Typsystems ist die Möglichkeit, den Kontext für numerische Literale über Einheiten festzulegen.

[Maßeinheiten](language-reference/units-of-measure.md) ermöglichen es Ihnen, einen numerischen Typ mit einer Einheit, z. B. Meter, zuordnen und haben Funktionen ausführen können numerische Literale, anstatt Einheiten.  Dadurch kann der Compiler, stellen Sie sicher, dass die Typen von numerischen Literalen übergebene sinnvoll unter einem bestimmten Kontext, somit-Runtime-Fehler dieser Art von Arbeit zugeordnet.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L818-L839)]

Die f#-Kernbibliothek definiert viele SI Einheitentypen und einheitenkonvertierungen.  Um mehr zu erfahren, sehen Sie sich die [Microsoft.FSharp.Data.UnitSystems.SI-Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Klassen und Schnittstellen

F# bietet auch vollständige Unterstützung für .NET-Klassen, [Schnittstellen](language-reference/interfaces.md), [abstrakte Klassen](language-reference/abstract-classes.md), [Vererbung](language-reference/inheritance.md)und so weiter.

[Klassen](language-reference/classes.md) sind Typen, die .NET-Objekten darstellen wofür können Eigenschaften, Methoden und Ereignisse als seine [Elemente](language-reference/members/index.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L848-L877)]

Definieren von generischen Klassen ist sehr einfach.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L884-L905)]

Um eine Schnittstelle zu implementieren, verwenden Sie entweder `interface ... with` Syntax oder einer [Objektausdruck](language-reference/object-expressions.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L912-L931)]

## <a name="which-types-to-use"></a>Welche Typen zu verwenden

Das Vorhandensein von Klassen, Datensätze und Unterscheidungs-Unions, Tupeln führt zu einer Kernfrage: welches sollten Sie verwenden?  Wie die meisten alles im Leben hängt Ihre Situation die Antwort.

Tupel sind hervorragend für mehrere Werte aus einer Funktion zurückgeben, und verwenden ein Ad-hoc-Aggregat von Werten als Wert selbst.

Eine "Step up" aus Tupeln, dass mit dem Namen Bezeichnungen und Unterstützung für optionale Elemente sind Datensätze.  Sie sind hervorragend für eine niedrige Zeremonie-Darstellung der Daten in Transit über das Programm.  Da sie Strukturgleichheit aufweisen, sind sie einfach zu verwenden, mit dem Vergleich.

Unterscheidungs-Unions sind vielseitig verwendbar, aber die Core Vorteil besteht darin, nutzen Sie diese in Verbindung mit dem Mustervergleich zum Konto für alle möglichen "Shapes", die über Daten verfügen können.  

Klassen sind hervorragend für eine Vielzahl von Gründen, z. B. Wenn Sie Informationen darstellen, und binden auch diese Informationen, um Funktionen müssen.  Als Faustregel gilt Wenn Sie Funktionen haben grundsätzlich auf einige Daten gebunden ist wird mithilfe von Klassen und die Prinzipien des objektorientiertes Programmieren ein großer Vorteil.  Klassen sind auch der bevorzugte Datentyp bei der Interaktion mit c# und Visual Basic, wie diese Sprachen für nahezu alles Klassen verwenden.

## <a name="next-steps"></a>Nächste Schritte

Nun, dass Sie einige der wichtigsten Features der Programmiersprache gesehen haben, sollten Sie zum Schreiben Ihrer ersten F#-Programs bereit sein!  Auschecken [Einstieg](tutorials/getting-started/index.md) erhalten Sie Informationen zum Einrichten Ihrer Entwicklungsumgebung und Code schreiben.

Die nächsten Schritte für weitere kann einen beliebigen Namen, aber es wird empfohlen [Funktionen als erstrangige Werte](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md)--> abzurufenden mit Kernkonzepte funktionale Programmierung vertraut.  Diese werden bei der Erstellung robuster ' Software ' in f# unentbehrlich.

Darüber hinaus sehen Sie sich die [f#-Sprachreferenz](language-reference/index.md) einem umfassenden Sortiment von konzeptuellen Inhalt in f# zu sehen.
