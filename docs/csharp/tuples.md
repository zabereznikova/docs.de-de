---
title: "Tupel | Leitfaden für C#"
description: "Erfahren Sie mehr über unbenannte und benannte Tupeltypen in C#"
keywords: .NET, .NET Core, C#
author: BillWagner
ms-author: wiwagn
ms.date: 11/23/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: ee8bf7c3-aa3e-4c9e-a5c6-e05cc6138baa
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b30f41e3fb07a962542a09a41c698efee7ebb5a
ms.openlocfilehash: 0ea7299d87dc69784e3bed93e48d83e4a0076a20
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---

# <a name="c-tuple-types"></a>C#-Tupeltypen #

C#-Tupel sind Typen, die Sie mithilfe einer einfachen Syntax definieren. Zu den Vorteilen gehören eine einfachere Syntax, Regeln für auf Zahlen basierte Umwandlungen (wird als „arity“ bezeichnet) und Typen von Feldern sowie konsistente Regeln für Kopien und Aufgaben. Dafür unterstützen Tupel nicht einige der objektorientierten Idiome, die der Vererbung zugeordnet werden. Sie erhalten im Abschnitt über Tupel im Thema [Neues in C# 7](whats-new/csharp-7.md#tuples) einen Überblick.

In diesem Thema lernen Sie die Sprachregeln, die Tupel in C# 7 steuern, verschiedene Verwendungsarten und einen ersten Leitfaden über das Arbeiten mit Tupel.

> [!NOTE]
> Die neuen Tupeleigenschaften benötigen den Typ `System.ValueTuple`. Sie müssen bei Visual Studio 2017 das NuGet-Paket [System.ValueTuple](https://www.nuget.org/packages/System.ValueTuple/) hinzufügen, das im NuGet-Katalog verfügbar ist.
> Ohne dieses Paket erhalten Sie vielleicht einen Kompilierungsfehler, der `error CS8179: Predefined type 'System.ValueTuple``2' is not defined or imported` oder `error CS8137: Cannot define a class or member that utilizes tuples because the compiler required type 'System.Runtime.CompilerServices.TupleElementNamesAttribute' cannot be found.` ähnelt

Beginnen wir mit den Gründen für das Hinzufügen von neuer Unterstützung für Tupel. Methoden geben ein einzelnes Objekt zurück. Mit Tupel können Sie mehrere Werte einfacher in das einzelne Objekt packen. 

.NET Framework hat bereits generische `Tuple`-Klassen. Diese Klassen hatten jedoch zwei wesentliche Einschränkungen. Zum einen haben die `Tuple`-Klassen ihre Felder als `Item1`, `Item2` usw. bezeichnet. Diese Namen enthalten keine semantischen Informationen. Mit diesen `Tuple`-Typen kann nicht die Bedeutung der einzelnen Felder kommuniziert werden. Ein weiterer Aspekt ist, dass die `Tuple`-Klassen Verweistypen sind. Das Verwenden von einem der `Tuple`-Typen bedeutet, dass Objekte zugeordnet werden. Auf dem langsamsten Pfad kann das einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben.

Sie können `class` oder `struct` zum Tragen von mehreren Feldern erstellen, um diese Mängel zu vermeiden. Leider bedeutet das mehr Arbeit für Sie, und es verdeckt Ihre Entwurfsabsicht. Durch das Erstellen von `struct` und `class` wird angedeutet, dass Sie einen Typ sowohl mit Daten als auch mit Verhalten definieren. In vielen Fällen möchten Sie einfach mehrere Werte in ein einzelnes Objekt speichern.

Die neuen Sprachfunktionen für Tupel zusammen mit einem neuen Klassensatz im Framework behandelt diese Mängel. Diese neuen Tupel verwenden die neuen generischen `ValueTuple`-Strukturen. Wie der Name schon sagt, ist dieser Typ `struct` anstatt `class`. Es gibt verschiedene Versionen dieser Struktur, um Tupel mit einer unterschiedlichen Anzahl von Feldern zu unterstützen. Die neue Sprachunterstützung stellt semantische Namen für die Felder des Tupeltyps bereit sowie Funktionen, die das Erstellen und den Zugriff auf Tupelfelder vereinfachen.

Die Sprachfunktionen und die generischen `ValueTuple`-Strukturen setzen die Regel durch, dass Sie nicht jedes beliebige Verhalten (Methoden) den Tupeltypen hinzufügen können.
Alle `ValueTuple`-Typen sind *veränderbare Strukturen*. Jedes Memberfeld ist ein öffentliches Feld. Das macht sie sehr einfach. Allerdings bedeutet dies, dass Tupel nicht dort verwendet werden dürfen, wo Unveränderlichkeit wichtig ist.

Tupel sind sowohl einfachere als auch flexiblere Datencontainer als `class`- und `struct`-Typen. Betrachten wir diese Unterschiede.

## <a name="named-and-unnamed-tuples"></a>Benannte und unbenannte Tupel

Die `ValueTuple`-Struktur hat Felder mit den Namen `Item1`, `Item2`, `Item3` usw, die den Eigenschaften ähnlich sind, die in den vorhandenen `Tuple`-Typen definiert wurden.
Diese Namen sind die einzigen Namen, die Sie für *unbenannte Tupel* verwenden können. Wenn Sie einem Tupel keine alternativen Feldnamen bereitstellen, haben Sie einen unbenannten Tupel erstellt:

[!code-csharp[UnnamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#01_UnNamedTuple "unbenannte Tupel")]

Sie können jedoch bei der Initialisierung eines Tupels neue Spracheigenschaften verwenden, die jedem Feld bessere Namen geben. Dadurch wird ein *benannter Tupel* erstellt.
Benannte Tupel haben immer noch Felder mit den Namen `Item1`, `Item2`, `Item3` usw.
Sie haben jedoch auch Synonyme für alle Felder, die Sie benannt haben.
Sie erstellen einen benannten Tupel, indem Sie den Namen für jedes Feld angeben. Eine Möglichkeit ist es, die Namen als Teil der Initialisierung des Tupel anzugeben:

[!code-csharp[NamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#02_NamedTuple "Benannter Tupel")]

Diese Synonyme werden vom Compiler und der Sprache verarbeitet, sodass Sie benannte Tupel effektiv verwenden können. IDEs und Editoren können die semantischen Namen mithilfe der Roslyn-APIs lesen. Dadurch können Sie die Felder eines benannten Tupels durch diese semantischen Namen an einer beliebigen Stelle in der gleichen Assembly verweisen. Der Compiler ersetzt die Namen, die Sie definiert haben, mit `Item*`-Äquivalenten, wenn die Compilerausgabe erzeugt wird. Die kompilierte Microsoft Intermediate Language (MSIL) enthält nicht die Namen, denen Sie diese Felder gegeben haben. 

Der Compiler muss diese Namen kommunizieren, die Sie für Tupel erstellt haben, die von öffentlichen Methoden oder Eigenschaften zurückgegeben wurden. In diesen Fällen fügt der Compiler ein Attribut `TupleElementNames` zur Methode hinzu. Dieses Attribut enthält eine `TransformNames`-Listeneigenschaft, die die Namen für jedes der Felder im Tupel enthält. 

> [!NOTE]
> Entwicklungstools wie Visual Studio lesen auch diese Metadaten und stellen IntelliSense und andere Funktionen bereit, die die Feldnamen der Metadaten verwenden.

Es ist wichtig, diese zugrunde liegenden Grundlagen der neuen Tupel sowie den `ValueTuple`-Typ zu verstehen, um die Regeln für das gegenseitige Zuweisen von benannten Tupel zu verstehen.

## <a name="assignment-and-tuples"></a>Zuweisung und Tupel

Die Sprache unterstützt die Zuweisung zwischen Tupeltypen, die über die gleiche Anzahl von Feldern und implizite Konvertierungen für die Typen für jedes dieser Felder verfügen. Andere Konvertierungen gelten nicht für Zuordnungen. Sehen wir uns die Arten von Zuweisungen an, die zwischen Tupeltypen zulässig sind.

Berücksichtigen Sie diese Variablen, die in den folgenden Beispielen verwendet werden:

[!code-csharp[VariableCreation](../../samples/snippets/csharp/tuples/tuples/program.cs#03_VariableCreation "Erstellung einer Variable")]

Die ersten zwei Variablen (`unnamed` und `anonymous`) haben keine semantische Namen für die Felder bereitgestellt. Die Feldnamen lauten `Item1` und `Item2`.
Die letzten zwei Variablen (`named` und `differentName`) habe semantische Namen für die Felder angegeben. Beachten Sie, dass diese zwei Tupel unterschiedliche Namen für die Felder besitzen.

Alle vier dieser Tupel haben die gleiche Anzahl von Felder (wird als „arity“ bezeichnet), und die Typen dieser Felder sind identisch. Daher funktionieren alle Zuweisungen:

[!code-csharp[VariableAssignment](../../samples/snippets/csharp/tuples/tuples/program.cs#04_VariableAssignment "Zuweisen einer Variable")]

Beachten Sie, dass die Namen der Tupel nicht zugewiesen sind. Die Werte der Felder werden nach der Reihenfolge der Felder im Tupel zugewiesen.

Tupel mit unterschiedlichen Typen oder mit einer unterschiedlichen Anzahl von Feldern sind nicht zuweisbar:

```csharp
// Does not compile.
// CS0029: Cannot assign Tuple(int,int,int) to Tuple(int, string)
var differentShape = (1, 2, 3);
named = differentShape;
```

## <a name="tuples-as-method-return-values"></a>Tupel als Methodenrückgabewert

Einer der häufigsten Verwendungszwecke für Tupel ist der Methodenrückgabewert. Lassen Sie uns ein ausführliches Beispiel ansehen. Betrachten Sie diese Methode, die die Standardabweichung für eine Sequenz von Zahlen berechnet:

[!code-csharp[StandardDeviation](../../samples/snippets/csharp/tuples/tuples/statistics.cs#05_StandardDeviation "Berechnen der Standardabweichung")]

> [!NOTE]
> In diesem Beispiel wird die unkorrigierte Beispielstandardabweichung berechnet.
> Die korrigierte Formel der Beispielstandardabweichung würde die Summe der Differenzen im Quadrat vom Mittelwert mithilfe von (N-1) anstatt N teilen, wie es die Erweiterungsmethode `Average` macht. Weitere Informationen zu den Unterschieden zwischen diesen Formeln für die Standardabweichung finden Sie in einem Statistiktext.

Dies entspricht der lehrbuchmäßigen Formel für die Standardabweichung. Die richtige Antwort wird generiert, aber es ist eine sehr ineffiziente Implementierung. Diese Methode listet die Sequenz zweimal auf: Einmal, um den Mittelwert zu erzeugen und einmal, um den Durchschnitt des Quadrats vom Unterschied des Durchschnitts zu erzeugen.
(Beachten Sie, dass LINQ-Abfragen verzögert ausgewertet werden. Daher kann die Berechnung der Unterschiede vom Mittelwert und des Durchschnitts dieser Unterschiede nur eine Enumeration erzeugen.)

Es gibt eine alternative Formel, die eine Standardabweichung anhand einer Enumeration der Sequenz berechnet.  Diese Berechnung erzeugt zwei Werte, da sie die Sequenz auflistet: Die Summe aller Elemente in der Sequenz und die Summe jedes Werts im Quadrat:

[!code-csharp[SumOfSquaresFormula](../../samples/snippets/csharp/tuples/tuples/statistics.cs#06_SumOfSquaresFormula "Berechnen der Standardabweichung mit der Quadratsumme")]

Diese Version listet die Sequenz genau einmal auf. Der Code kann jedoch nicht wirklich wieder verwendet werden. Während Sie arbeiten, werden Sie sehen, dass viele unterschiedliche statistische Berechnungen die Anzahl von Elementen in der Sequenz, die Summe der Sequenzen und die Summe der Quadrate der Sequenz verwenden. Gestalten Sie diese Methode um und schreiben Sie eine Hilfsmethode, die alle diese Werte erzeugt.

Dafür sind Tupel sehr nützlich. 

Wir aktualisieren diese Methoden, sodass die drei Werte, die während der Enumeration berechnet werden, in einem Tupel gespeichert werden. Dadurch wird diese Version erstellt:

[!code-csharp[TupleVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#07_TupleVersion "Umgestaltung zur Verwendung von Tupel")]

Die Unterstützung von Refactoring von Visual Studio vereinfacht es, die Funktionalität für die Kernstatistik in eine private Methode zu extrahieren. Das gibt Ihnen eine `private static`-Methode, die den Tupeltyp mit den drei Werten von `Sum`, `SumOfSquares` und `Count` zurückgibt:

[!code-csharp[TupleMethodVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#08_TupleMethodVersion "Nach dem Extrahieren der Hilfsmethode")]
 
Die Sprache aktiviert einige weitere Optionen, die Sie verwenden können, wenn Sie ein Paar schnelle manuelle Bearbeitungen vornehmen möchten. Sie können zuerst die Deklaration `var` verwenden, um das Tupelergebnis vom Methodenaufruf `ComputeSumAndSumOfSquares` zu initialisieren. Sie können auch drei diskrete Variablen in der Methode `ComputeSumAndSumOfSquares` erstellen. Die endgültige Version ist wie folgt:

[!code-csharp[CleanedTupleVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#09_CleanedTupleVersion "Nach der letzten Bereinigung")]

Die endgültige Version kann für jede Methode, die diese drei Werte oder einen Teil davon benötigt, verwendet werden.

Die Sprache unterstützt andere Optionen, indem sie die Namen der Felder in diesen Methoden verwaltet, die Tupel zurückgeben.

Sie können die Feldnamen aus der Deklaration des Rückgabewerts entfernen und einen unbenannten Tupel zurückgeben:

```csharp
private static (double, double, int) ComputeSumAndSumOfSquares(IEnumerable<double> sequence)
{
    double sum = 0;
    double sumOfSquares = 0;
    int count = 0;

    foreach (var item in sequence)
    {
        count++;
        sum += item;
        sumOfSquares += item * item;
    }

    return (sum, sumOfSquares, count);
}
```

Sie müssen die Felder dieses Tupels als `Item1`, `Item2` und `Item3` behandeln.
Es wird empfohlen, dass Sie den Tupelfeldern, die von Methoden zurückgegeben werden, semantische Namen bereitstellen.

Eine anderes Idiom, in dem Tupel sehr nützlich sein könnten, ist beim Verfassen von LINQ-Abfragen, bei denen das endgültige Ergebnis eine Projektion ist, die einige – aber nicht alle – Eigenschaften der ausgewählten Objekte enthält.

Sie würden normalerweise die Abfrageergebnisse in eine Sequenz von Objekten projizieren, die ein anonymer Typ waren. Das stellte viele Einschränkungen dar, hauptsächlich, weil anonyme Typen nicht bequem im Rückgabetyp für eine Methode benannt werden konnten. Alternativen, in denen `object` und `dynamic` als Typ des Ergebnisses verwende wurden, gingen mit erheblichen Leistungseinbußen einher.

Das Zurückgeben einer Sequenz eines Tupeltyps ist einfach, und die Namen und Typen der Felder sind zur Kompilierzeit und über die IDE-Tools verfügbar.
Betrachten Sie z B. eine ToDo-Anwendung. Sie könnten eine Klassen vielleicht so ähnlich wie folgt definieren, um einen einzelnen Eintrag in der ToDo-Liste darzustellen:

[!code-csharp[ToDoItem](../../samples/snippets/csharp/tuples/tuples/projectionsample.cs#14_ToDoItem "To-Do-Element")]

Ihre mobile Anwendung unterstützt vielleicht ein kompaktes Format der aktuellen ToDo-Elemente, die nur den Titel anzeigen. LINQ-Abfragen würden eine Projektion erstellen, die nur die ID und den Titel enthält. Eine Methode, die eine Tupelsequenz zurückgibt, drückt den Entwurf sehr gut aus:

[!code-csharp[QueryReturningTuple](../../samples/snippets/csharp/tuples/tuples/projectionsample.cs#15_QueryReturningTuple "Abfrage, die ein Tupel zurückgibt")]

Das benannte Tupel kann Teil der Signatur sein. Es lässt den Compiler und IDE-Tools statisch bereitstellen, indem überprüft wird, ob Sie das Ergebnis richtig verwenden. Das benannte Tupel trägt auch die statischen Typinformationen, sodass keine teuren Laufzeitfunktionen wie Reflektion oder dynamische Bindung verwendet werden müssen, um mit den Ergebnissen zu arbeiten.

## <a name="deconstruction"></a>Dekonstruktion

Sie können alle Elemente in einem Tupel entpacken, indem das Tupel, das von einer Methode zurückgegeben wurde, *dekonstruiert* wird. Es gibt zwei unterschiedliche Ansätze zum Dekonstruieren von Tupeln.  Zuerst können Sie ausdrücklich den Typ von jedem Feld in Klammern deklarieren, um diskrete Variablen für jedes der Felder im Tupel zu erstellen:

[!code-csharp[Deconstruct](../../samples/snippets/csharp/tuples/tuples/statistics.cs#10_Deconstruct "Dekonstruieren")]

Sie können auch typisierte Variablen für jedes Feld in ein Tupel deklarieren, indem das Schlüsselwort `var` außerhalb der Klammern verwendet wird:

[!code-csharp[DeconstructToVar](../../samples/snippets/csharp/tuples/tuples/statistics.cs#11_DeconstructToVar "Dekonstruieren nach Var")]

Das Verwenden des Schlüsselworts `var` mit beliebigen oder allen Variablendeklarationen in den Klammern ist auch zulässig. 

```csharp
(double sum, var sumOfSquares, var count) = ComputeSumAndSumOfSquares(sequence);
```
Beachten Sie, dass Sie einen bestimmten Typ außerhalb der Klammern verwenden können, auch wenn jedes Feld im Tupel den selben Typ hat.

### <a name="deconstructing-user-defined-types"></a>Dekonstruieren von benutzerdefinierten Typen

Jeder Tupeltyp kann dekonstruiert werden, wie oben gezeigt wurde. Es ist genau so einfach, die Dekonstruktion in beliebigen benutzerdefinierten Typen (Klassen, Strukturen oder sogar Oberflächen) zu aktivieren.

Der Autor des Typs kann eine oder mehrere `Deconstruct`-Methoden definieren, die einer beliebigen Anzahl von `out`-Variablen Werte zuweisen, die die Datenelemente darstellen, die den Typ ausmachen. Der folgende `Person`-Typ definiert z.B. eine `Deconstruct`-Methode, die ein Personenobjekt in die Felder dekonstruiert, die dem Vor- und Nachnamen entsprechen:

[!code-csharp[TypeWithDeconstructMethod](../../samples/snippets/csharp/tuples/tuples/person.cs#12_TypeWithDeconstructMethod "Typ mit einer Dekonstruktionsmethode")]

Die Dekonstruktionsmethode ermöglicht die Zuordnung von einer `Person` zu zwei Zeichenfolgen, die die Eigenschaften `FirstName` und `LastName` darstellen:

[!code-csharp[Deconstruct Type](../../samples/snippets/csharp/tuples/tuples/program.cs#12A_DeconstructType "Dekonstruieren von einem Klassentyp")]

Sie können Dekonstruktion selbst für Typen aktivieren, die Sie nicht geschrieben haben.
Die `Deconstruct`-Methode kann eine Erweiterungsmethode sein, die die zugänglichen Datenmember eines Objekts entpackt. Das folgende Beispiel zeigt einen `Student`-Typ, der vom `Person`-Typ abgeleitet wurde, sowie eine Erweiterungsmethode, die ein `Student` in drei Variablen dekonstruiert, die den `FirstName`, `LastName` und `GPA` darstellen:

[!code-csharp[ExtensionDeconstructMethod](../../samples/snippets/csharp/tuples/tuples/person.cs#13_ExtensionDeconstructMethod "Typ mit einer Dekonstruktionserweiterungsmethode")]

Ein `Student`-Objekt hat jetzt zwei zugängliche `Deconstruct`-Methoden: Die Erweiterungsmethode, die für `Student`-Typen deklariert wurde, und die Member des `Person`-Typs. Beide befinden sich im Geltungsbereich, womit ein `Student` entweder in zwei oder drei Variablen dekonstruiert werden kann.
Wenn Sie einem Studenten drei Variablen zuweisen, werden Vorname, Nachname sowie das GPA zurückgegeben. Wenn Sie einem Studenten zwei Variablen zuweisen, werden nur Vor- und Nachname zurückgegeben.

[!code-csharp[Deconstruct extension method](../../samples/snippets/csharp/tuples/tuples/program.cs#13A_DeconstructExtension "Dekonstruieren eines Klassentyps mithilfe einer Erweiterungsmethode")]

Sie sollten sehr vorsichtig mit dem Definieren von mehreren `Deconstruct`-Methoden in einer Klasse oder einer Klassenhierarchie sein. Mehrere `Deconstruct`-Methoden, die die gleiche Anzahl von `out`-Parameter haben, können schnell zu Mehrdeutigkeiten führen. Aufrufer können dann vielleicht nicht die gewünschte `Deconstruct`-Methode aufrufen.

In diesem Beispiel besteht minimale Wahrscheinlichkeit für einen mehrdeutigen Aufruf, weil die `Deconstruct`-Methode für `Person` zwei Ausgabeparameter besitzt, und die `Deconstruct`-Methode für `Student` drei besitzt.

## <a name="conclusion"></a>Schlussfolgerung 

Die neue Sprach- und Bibliotheksunterstützung für benannte Tupel vereinfacht es, mit Entwürfen zu arbeiten, die Datenstrukturen verwenden, die mehrere Felder definieren, aber keine Verhalten definieren, wie es Klassen und Strukturen tun. Die Verwendung von Tupeln ist für diese Typen einfach und präzise. Sie erhalten alle Vorteile der Überprüfung von statischen Typen, ohne Typen mithilfe der ausführlicheren `class`- oder `struct`-Syntax schreiben zu müssen. Dennoch sind sie für Hilfsmethoden, die `private` oder `internal` sind, am nützlichsten. Erstellen Sie benutzerdefinierte Typen, entweder Typen `class` oder `struct`, wenn Ihre öffentlichen Methoden einen Wert mit mehreren Feldern zurückgibt.

