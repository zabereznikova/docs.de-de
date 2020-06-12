---
title: Tupeltypen | C#-Leitfaden
description: Erfahren Sie mehr über unbenannte und benannte Tupeltypen in C#
ms.date: 05/15/2018
ms.technology: csharp-fundamentals
ms.assetid: ee8bf7c3-aa3e-4c9e-a5c6-e05cc6138baa
ms.openlocfilehash: 497f95811677c300e1fadad65eb495dced7f2da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374615"
---
# <a name="c-tuple-types"></a>C#-Tupeltypen

C#-Tupel sind Typen, die Sie mithilfe einer einfachen Syntax definieren. Zu den Vorteilen gehören eine einfachere Syntax, Regeln für auf Zahlen basierte Umwandlungen (sogenannte Kardinalitäten) und Typen von Elementen sowie konsistente Regeln für Kopien, Gleichheitstests und Aufgaben. Dafür unterstützen Tupel nicht einige der objektorientierten Idiome, die der Vererbung zugeordnet werden. Sie erhalten im Abschnitt zu Tupeln im Artikel [Neuerungen in C# 7.0](whats-new/csharp-7.md#tuples) einen Überblick.

In diesem Artikel erhalten Sie Informationen zu Sprachregeln, die Tupel in C# 7.0 und höheren Versionen steuern und zu verschiedenen Verwendungsarten. Außerdem wird ein erster Leitfaden zum Arbeiten mit Tupeln zur Verfügung gestellt.

> [!NOTE]
> Die neuen Tupeleigenschaften benötigen die <xref:System.ValueTuple>-Typen.
> Sie müssen das NuGet-Paket [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) hinzufügen, um es auf Plattformen zu verwenden, die keine Typen enthalten.
>
> Dies ist ähnlich wie bei anderen Sprachfunktionen, die auf im Framework übermittelten Typen basieren. Beispiele hierfür sind `async` und `await`, die auf der `INotifyCompletion`-Schnittstelle basieren, und LINQ, das auf `IEnumerable<T>` basiert. Allerdings ändert sich der Übermittlungsmechanismus, da .NET plattformunabhängiger wird. .NET Framework wird möglicherweise nicht immer im gleichen Rhythmus wie der Sprachcompiler ausgeliefert. Wenn neue Sprachfunktionen auf neuen Typen basieren, sind diese Typen als NuGet-Pakete bei der Auslieferung der Sprachfunktionen verfügbar. Da diese neuen Typen dem standardmäßigen .NET API hinzugefügt und als Teil des Frameworks bereitgestellt werden, wird die Anforderung des NuGet-Pakets entfernt.

Beginnen wir mit den Gründen für das Hinzufügen neuer Unterstützung für Tupel. Methoden geben ein einzelnes Objekt zurück. Mit Tupel können Sie mehrere Werte einfacher in das einzelne Objekt packen.

.NET Framework hat bereits generische `Tuple`-Klassen. Diese Klassen hatten jedoch zwei wesentliche Einschränkungen. Zum einen haben die `Tuple`-Klassen ihre Eigenschaften als `Item1`, `Item2` usw. bezeichnet. Diese Namen enthalten keine semantischen Informationen. Mit diesen `Tuple`-Typen kann nicht die Bedeutung der einzelnen Eigenschaften kommuniziert werden. Die neuen Sprachfeatures ermöglichen Ihnen, semantisch aussagekräftige Namen für die Elemente eines Tupels zu deklarieren und zu verwenden.

Die `Tuple`-Klassen verursachen mehr Bedenken bezüglich der Leistung, da es sich dabei um Verweistypen handelt. Das Verwenden von einem der `Tuple`-Typen bedeutet, dass Objekte zugeordnet werden. Bei langsamen Pfaden kann das Zuordnen vieler kleiner Objekte einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben. Deshalb nutzt die Sprachunterstützung für Tupels die neuen `ValueTuple`-Strukturen.

Sie können `class` oder `struct` zum Tragen von mehreren Elementen erstellen, um diese Mängel zu vermeiden. Leider bedeutet das mehr Arbeit für Sie, und es verdeckt Ihre Entwurfsabsicht. Durch das Erstellen von `struct` und `class` wird angedeutet, dass Sie einen Typ sowohl mit Daten als auch mit Verhalten definieren. In vielen Fällen möchten Sie einfach mehrere Werte in ein einzelnes Objekt speichern.

Die Sprachfunktionen und die generischen `ValueTuple`-Strukturen setzen die Regel durch, dass Sie nicht jedes beliebige Verhalten (Methoden) den Tupeltypen hinzufügen können.
Alle `ValueTuple`-Typen sind *veränderbare Strukturen*. Jedes Memberfeld ist ein öffentliches Feld. Das macht sie sehr einfach. Allerdings bedeutet dies, dass Tupel nicht dort verwendet werden dürfen, wo Unveränderlichkeit wichtig ist.

Tupel sind sowohl einfachere als auch flexiblere Datencontainer als `class`- und `struct`-Typen. Betrachten wir diese Unterschiede.

## <a name="named-and-unnamed-tuples"></a>Benannte und unbenannte Tupel

Die `ValueTuple`-Struktur hat Felder mit den Namen `Item1`, `Item2`, `Item3` usw., die den Eigenschaften ähnlich sind, die in den vorhandenen `Tuple`-Typen definiert wurden.
Diese Namen sind die einzigen Namen, die Sie für *unbenannte Tupel* verwenden können. Wenn Sie einem Tupel keine alternativen Feldnamen bereitstellen, haben Sie einen unbenannten Tupel erstellt:

[!code-csharp[UnnamedTuple](../../samples/snippets/csharp/tuples/program.cs#01_UnNamedTuple "Unnamed tuple")]

Das Tupel im vorherigen Beispiel wurde mithilfe von Literalkonstanten initialisiert und verfügt nicht über Elementnamen, die mithilfe von *Projektionen für Tupel-Feldnamen* in C# 7.1 erstellt wurden.

Sie können jedoch bei der Initialisierung eines Tupels neue Spracheigenschaften verwenden, die jedem Feld bessere Namen geben. Dadurch wird ein *benannter Tupel* erstellt.
Benannte Tupel haben immer noch Elemente mit den Namen `Item1`, `Item2`, `Item3` usw.
Sie haben jedoch auch Synonyme für alle Elemente, die Sie benannt haben.
Sie erstellen einen benannten Tupel, indem Sie den Namen für jedes Element angeben. Eine Möglichkeit ist es, die Namen als Teil der Initialisierung des Tupel anzugeben:

[!code-csharp[NamedTuple](../../samples/snippets/csharp/tuples/program.cs#02_NamedTuple "Named tuple")]

Diese Synonyme werden vom Compiler und der Sprache verarbeitet, sodass Sie benannte Tupel effektiv verwenden können. IDEs und Editoren können die semantischen Namen mithilfe der Roslyn-APIs lesen. Sie können auf die Elemente eines benannten Tupels durch diese semantischen Namen an einer beliebigen Stelle in der gleichen Assembly verweisen. Der Compiler ersetzt die Namen, die Sie definiert haben, mit `Item*`-Äquivalenten, wenn die Compilerausgabe erzeugt wird. Die kompilierte Microsoft Intermediate Language (MSIL) enthält nicht die Namen, die Sie diesen Elementen gegeben haben.

Ab C# 7.1 können die Feldnamen für ein Tupel von den Variablen bereitgestellt werden, die zum Initialisieren des Tupels verwendet werden. Diese werden als **[Tupel-Projektionsinitialisierer](#tuple-projection-initializers)** bezeichnet. Der folgende Code erstellt ein Tupel namens `accumulation` mit den Elementen `count` (ein integer-Typ Zahl) und `sum` (ein Double-Typ).

[!code-csharp[ProjectedTuple](../../samples/snippets/csharp/tuples/program.cs#ProjectedTupleNames "Named tuple")]

Der Compiler muss diese Namen kommunizieren, die Sie für Tupel erstellt haben, die von öffentlichen Methoden oder Eigenschaften zurückgegeben wurden. In diesen Fällen fügt der Compiler ein Attribut <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute> zur Methode hinzu. Dieses Attribut enthält eine <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute.TransformNames>-Listeneigenschaft, die die Namen für jedes der Elemente im Tupel enthält.

> [!NOTE]
> Entwicklungstools wie Visual Studio lesen auch diese Metadaten und stellen IntelliSense und andere Funktionen bereit, die die Feldnamen der Metadaten verwenden.

Es ist wichtig, diese zugrunde liegenden Grundlagen der neuen Tupel sowie den `ValueTuple`-Typ zu verstehen, um die Regeln für das gegenseitige Zuweisen von benannten Tupel zu verstehen.

## <a name="tuple-projection-initializers"></a>Tupel-Projektionsinitialisierer

Im allgemeinen funktionieren Tupel-Projektionsinitialisierer, indem die Variablen- oder Feldnamen von der rechten Seite der Initialisierungsanweisung eines Tupels verwendet werden.
Wenn ein expliziter Name vergeben wird, hat dieser vor jedem projizierten Namen Vorrang. Im folgenden Initialisierer sind die Elemente beispielsweise `explicitFieldOne` und `explicitFieldTwo`, nicht `localVariableOne` und `localVariableTwo`:

[!code-csharp[ExplicitNamedTuple](../../samples/snippets/csharp/tuples/program.cs#ProjectionExample_Explicit "Explicitly named tuple")]

Für jedes Feld ohne expliziten Namen wird ein zutreffender, impliziter Name projiziert. Es ist weder explizit noch implizit nötig, semantische Namen bereitzustellen. Der folgende Initialisierer besitzt den Feldnamen `Item1`, dessen Wert `42` ist, und `stringContent`, dessen Wert „Die Antwort auf alles“ ist:

[!code-csharp[MixedTuple](../../samples/snippets/csharp/tuples/program.cs#MixedTuple "mixed tuple")]

Es gibt zwei Bedingungen, unter denen die Feldnamen von Kandidaten nicht auf das Tupelfeld projiziert werden:

1. Wenn es sich beim Namen des Kandidaten um einen reservierten Tupelnamen handelt. Die Beispiele umfassen `Item3`, `ToString` oder `Rest`.
1. Wenn es sich beim Namen des Kandidaten um das Duplikat des expliziten oder impliziten Feldnamens eines anderen Tupels handelt.

Durch diese Bedingungen wird Mehrdeutigkeit vermieden. Diese Namen würden eine Mehrdeutigkeit verursachen, wenn sie als Feldnamen für das Feld eines Tupels verwendet würden. Keine dieser Bedingungen verursacht Kompilierzeitfehler. Stattdessen werden für die Elemente, die nicht über projizierte Namen verfügen, keine semantischen Namen projiziert.  In den folgenden Beispielen werden diese Bedingungen veranschaulicht:

[!code-csharp-interactive[Ambiguity](../../samples/snippets/csharp/tuples/program.cs#ProjectionAmbiguities "tuples where projections are not performed")]

Diese Situationen verursachen keine Compilerfehler, da diese eine grundlegende Änderung für mit C# 7.0 geschriebenen Code darstellen würden, bei dem die Projektionen für Tupel-Feldnamen noch nicht verfügbar waren.

## <a name="equality-and-tuples"></a>Gleichheit und Tupel

Ab C# 7.3 unterstützen Tupeltypen die Operatoren `==` und `!=`. Diese Operatoren arbeiten durch Vergleichen jedes Members des linken Arguments mit jedem Member des rechten Arguments in der Reihenfolge. Diese Vergleiche können verkürzt werden. Sie beenden die Auswertung von Membern, sobald ein Paar nicht gleich ist. In folgendem Codebeispiel wird `==` verwendet, die Vergleichsregeln gelten jedoch alle für `!=`. Das folgende Codebeispiel stellt einen Gleichheitsvergleich für zwei Paare ganzer Zahlen dar:

[!code-csharp-interactive[TupleEquality](../../samples/snippets/csharp/tuples/program.cs#Equality "Testing tuples for equality")]

Es gibt einige Regeln, die Tupelgleichheitstests einfacher machen. Die Tupelgleichheit führt [mehrstufige Konvertierungen](~/_csharplang/spec/conversions.md#lifted-conversion-operators) aus, wenn eines der Tupel ein Tupel mit NULL-Werten ist, so wie im folgenden Code dargestellt:

[!code-csharp-interactive[NullableTupleEquality](../../samples/snippets/csharp/tuples/program.cs#NullableEquality "Comparing Tuples and nullable tuples")]

Die Tupelgleichheit führt ebenso implizite Konvertierungen für jeden Member beider Tupel aus. Dazu gehören mehrstufige Konvertierungen, Erweiterungskonvertierungen oder andere implizite Konvertierungen. Die folgenden zwei Beispiele zeigen, dass ein ganzzahliges 2-Tupel mit einem langen 2-Tupel aufgrund der impliziten Konvertierung von „integer“ in „long“ verglichen werden kann.

[!code-csharp-interactive[SnippetMemberConversions](../../samples/snippets/csharp/tuples/program.cs#SnippetMemberConversions "converting tuples for equality tests")]

Die Namen der Tupelmember sind nicht Teil von Tests auf Gleichheit. Wenn jedoch einer der Operanden ein Tupelliteral mit expliziten Namen ist, generiert der Compiler die Warnung CS8383, wenn diese Namen nicht mit den Namen des anderen Operanden übereinstimmen.
Sobald beide Operanden Tupelliterale sind, befindet sich die Warnung beim rechten Operanden, wie im folgenden Beispiel gezeigt:

[!code-csharp-interactive[MemberNames](../../samples/snippets/csharp/tuples/program.cs#SnippetMemberNames "Tuple member names do not participate in equality tests")]

Zuletzt können Tupel geschachtelte Tupel enthalten. Die Tupelgleichheit vergleicht die „Form“ jedes Operanden, wie im folgenden Beispiel dargestellt, über geschachtelte Tupel:

[!code-csharp-interactive[NestedTuples](../../samples/snippets/csharp/tuples/program.cs#SnippetNestedTuples "Tuples may contain nested tuples that participate in tuple equality.")]

Beim Vergleich zweier Tupel für Gleichheit (oder Ungleichheit) tritt zur Kompilierzeit ein Fehler auf, wenn sie verschiedene Formen aufweisen. Der Compiler unternimmt keinen Dekonstruktionsversuch für geschachtelte Tupel, um diese zu vergleichen.

## <a name="assignment-and-tuples"></a>Zuweisung und Tupel

Die Sprache unterstützt die Zuordnung zwischen Tupeltypen, die über die gleiche Anzahl von Elementen verfügen, wobei jedes Element auf der rechten Seite implizit in sein entsprechendes linkes Element konvertiert werden kann. Andere Konvertierungen werden für Zuweisungen nicht in Betracht gezogen. Bei der Zuweisung eines Tupels zu einem anderen tritt zur Kompilierzeit ein Fehler auf, wenn sie verschiedene Formen aufweisen. Der Compiler unternimmt keinen Dekonstruktionsversuch für geschachtelte Tupel, um diese zu zuzuweisen.
Sehen wir uns die Arten von Zuweisungen an, die zwischen Tupeltypen zulässig sind.

Berücksichtigen Sie diese Variablen, die in den folgenden Beispielen verwendet werden:

[!code-csharp[VariableCreation](../../samples/snippets/csharp/tuples/program.cs#03_VariableCreation "Variable creation")]

Die ersten zwei Variablen (`unnamed` und `anonymous`) haben keine semantischen Namen für die Elemente bereitgestellt. Die Feldnamen lauten `Item1` und `Item2`.
Die letzten zwei Variablen (`named` und `differentName`) haben semantische Namen für die Elemente angegeben. Diese zwei Tupel besitzen unterschiedliche Namen für die Elemente.

Alle vier dieser Tupel haben die gleiche Anzahl von Elementen (als „Kardinalität“ bezeichnet), und die Typen dieser Elemente sind identisch. Daher funktionieren alle Zuweisungen:

[!code-csharp[VariableAssignment](../../samples/snippets/csharp/tuples/program.cs#04_VariableAssignment "Variable assignment")]

Beachten Sie, dass die Namen der Tupel nicht zugewiesen sind. Die Werte der Elemente werden nach der Reihenfolge der Elemente im Tupel zugewiesen.

Tupel mit unterschiedlichen Typen oder mit einer unterschiedlichen Anzahl von Elementen sind nicht zuweisbar:

```csharp
// Does not compile.
// CS0029: Cannot assign Tuple(int,int,int) to Tuple(int, string)
var differentShape = (1, 2, 3);
named = differentShape;
```

## <a name="tuples-as-method-return-values"></a>Tupel als Methodenrückgabewert

Einer der häufigsten Verwendungszwecke für Tupel ist als Methodenrückgabewerte. Lassen Sie uns ein ausführliches Beispiel ansehen. Betrachten Sie diese Methode, die die Standardabweichung für eine Sequenz von Zahlen berechnet:

[!code-csharp[StandardDeviation](../../samples/snippets/csharp/tuples/statistics.cs#05_StandardDeviation "Compute Standard Deviation")]

> [!NOTE]
> In diesem Beispiel wird die unkorrigierte Beispielstandardabweichung berechnet.
> Die korrigierte Formel der Beispielstandardabweichung würde die Summe der Differenzen im Quadrat vom Mittelwert mithilfe von (N-1) anstatt N teilen, wie es die Erweiterungsmethode `Average` macht. Weitere Informationen zu den Unterschieden zwischen diesen Formeln für die Standardabweichung finden Sie in einem Statistiktext.

Der vorangehende Code entspricht der idealen Formel für die Standardabweichung. Die richtige Antwort wird generiert, aber es ist eine ineffiziente Implementierung. Diese Methode listet die Sequenz zweimal auf: Einmal, um den Durchschnitt zu erzeugen, und einmal, um den Durchschnitt des Quadrats der Differenz des Durchschnitts zu erzeugen.
(Beachten Sie, dass LINQ-Abfragen verzögert ausgewertet werden. Daher kann die Berechnung der Unterschiede vom Mittelwert und des Durchschnitts dieser Unterschiede nur eine Enumeration erzeugen.)

Es gibt eine alternative Formel, die eine Standardabweichung anhand einer Enumeration der Sequenz berechnet.  Diese Berechnung erzeugt zwei Werte, da sie die Sequenz auflistet: Die Summe aller Elemente in der Sequenz und die Summe jedes Werts im Quadrat:

[!code-csharp[SumOfSquaresFormula](../../samples/snippets/csharp/tuples/statistics.cs#06_SumOfSquaresFormula "Compute Standard Deviation using the sum of squares")]

Diese Version listet die Sequenz genau einmal auf. Der Code kann jedoch nicht wieder verwendet werden. Während Sie arbeiten, werden Sie sehen, dass viele unterschiedliche statistische Berechnungen die Anzahl von Elementen in der Sequenz, die Summe der Sequenzen und die Summe der Quadrate der Sequenz verwenden. Gestalten Sie diese Methode um und schreiben Sie eine Hilfsmethode, die alle diese Werte erzeugt. Alle drei Werte können als Tupel zurückgegeben werden.

Wir aktualisieren diese Methoden, sodass die drei Werte, die während der Enumeration berechnet werden, in einem Tupel gespeichert werden. Dadurch wird diese Version erstellt:

[!code-csharp[TupleVersion](../../samples/snippets/csharp/tuples/statistics.cs#07_TupleVersion "Refactor to use tuples")]

Die Unterstützung von Refactoring in Visual Studio vereinfacht es, die Funktionen für die Kernstatistik in eine private Methode zu extrahieren. Das gibt Ihnen eine `private static`-Methode, die den Tupeltyp mit den drei Werten von `Sum`, `SumOfSquares` und `Count` zurückgibt:

[!code-csharp[TupleMethodVersion](../../samples/snippets/csharp/tuples/statistics.cs#08_TupleMethodVersion "After extracting utility method")]

Die Sprache aktiviert einige weitere Optionen, die Sie verwenden können, wenn Sie ein Paar schnelle manuelle Bearbeitungen vornehmen möchten. Sie können zuerst die Deklaration `var` verwenden, um das Tupelergebnis vom Methodenaufruf `ComputeSumAndSumOfSquares` zu initialisieren. Sie können auch drei diskrete Variablen in der Methode `ComputeSumAndSumOfSquares` erstellen. Die finale Version wird im folgenden Beispielcode dargestellt:

[!code-csharp[CleanedTupleVersion](../../samples/snippets/csharp/tuples/statistics.cs#09_CleanedTupleVersion "After final cleanup")]

Die endgültige Version kann für jede Methode, die diese drei Werte oder einen Teil davon benötigt, verwendet werden.

Die Sprache unterstützt andere Optionen, indem sie die Namen der Elemente in diesen Methoden verwaltet, die Tupel zurückgeben.

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

Die Felder für dieses Tupel heißen `Item1`, `Item2` und `Item3`.
Es wird empfohlen, dass Sie den Tupelelementen, die von Methoden zurückgegeben werden, semantische Namen bereitstellen.

Ein anderes Idiom, für das Tupel nützlich sein können, ist beim Erstellen von LINQ-Abfragen. Das letztendlich projizierte Ergebnis enthält oft einige (aber nicht alle) Eigenschaften des Objekts, die ausgewählt werden.

Sie würden normalerweise die Abfrageergebnisse in eine Sequenz von Objekten projizieren, die ein anonymer Typ waren. Das stellte viele Einschränkungen dar, hauptsächlich, weil anonyme Typen nicht bequem im Rückgabetyp für eine Methode benannt werden konnten. Alternativen, in denen `object` und `dynamic` als Typ des Ergebnisses verwende wurden, gingen mit erheblichen Leistungseinbußen einher.

Das Zurückgeben einer Sequenz eines Tupeltyps ist einfach, und die Namen und Typen der Elemente sind zur Kompilierzeit und über die IDE-Tools verfügbar.
Betrachten Sie z B. eine ToDo-Anwendung. Sie könnten eine Klassen vielleicht so ähnlich wie folgt definieren, um einen einzelnen Eintrag in der ToDo-Liste darzustellen:

[!code-csharp[ToDoItem](../../samples/snippets/csharp/tuples/projectionsample.cs#14_ToDoItem "To Do Item")]

Ihre mobile Anwendung unterstützt vielleicht ein kompaktes Format der aktuellen ToDo-Elemente, die nur den Titel anzeigen. LINQ-Abfragen würden eine Projektion erstellen, die nur die ID und den Titel enthält. Eine Methode, die eine Tupelsequenz zurückgibt, drückt den Entwurf gut aus:

[!code-csharp[QueryReturningTuple](../../samples/snippets/csharp/tuples/projectionsample.cs#15_QueryReturningTuple "Query returning a tuple")]

> [!NOTE]
> In C# 7.1 ermöglichen Tupelprojektionen Ihnen das Erstellen benannter Tupel mithilfe von Elementen, ähnlich wie beim Benennen von Eigenschaften bei anonymen Typen. Im obigen Code erstellt die `select`-Anweisung in der Abfrageprojektionen ein Tupel, das die Elemente `ID` und `Title` besitzt.

Das benannte Tupel kann Teil der Signatur sein. Es lässt den Compiler und IDE-Tools statisch bereitstellen, indem überprüft wird, ob Sie das Ergebnis richtig verwenden. Das benannte Tupel trägt auch die statischen Typinformationen, sodass keine teuren Laufzeitfunktionen wie Reflektion oder dynamische Bindung verwendet werden müssen, um mit den Ergebnissen zu arbeiten.

## <a name="deconstruction"></a>Dekonstruktion

Sie können alle Elemente in einem Tupel entpacken, indem das Tupel, das von einer Methode zurückgegeben wurde, *dekonstruiert* wird. Es gibt drei verschiedene Ansätze zum Dekonstruieren von Tupeln.  Zuerst können Sie ausdrücklich den Typ von jedem Feld in Klammern deklarieren, um diskrete Variablen für jedes der Elemente im Tupel zu erstellen:

[!code-csharp[Deconstruct](../../samples/snippets/csharp/tuples/statistics.cs#10_Deconstruct "Deconstruct")]

Sie können auch typisierte Variablen für jedes Feld in ein Tupel deklarieren, indem das Schlüsselwort `var` außerhalb der Klammern verwendet wird:

[!code-csharp[DeconstructToVar](../../samples/snippets/csharp/tuples/statistics.cs#11_DeconstructToVar "Deconstruct to Var")]

Das Verwenden des Schlüsselworts `var` mit beliebigen oder allen Variablendeklarationen in den Klammern ist auch zulässig.

```csharp
(double sum, var sumOfSquares, var count) = ComputeSumAndSumOfSquares(sequence);
```

Sie können einen bestimmten Typ außerhalb der Klammern verwenden, auch wenn jedes Feld im Tupel den selben Typ hat.

Sie können Tupel auch mit bereits vorhandenen Deklarationen dekonstruieren:

```csharp
public class Point
{
    public int X { get; set; }
    public int Y { get; set; }

    public Point(int x, int y) => (X, Y) = (x, y);
}
```

> [!WARNING]
> Allerdings können bereits vorhandene Deklarationen nicht mit Deklarationen vermischt werden, die in Klammern stehen. Folgendes ist beispielsweise nicht erlaubt: `(var x, y) = MyMethod();`. Dadurch wird der Fehler CS8184 ausgelöst, da *x* in Klammern und *y* bereits zuvor an einer anderen Stelle deklariert wurden.

### <a name="deconstructing-user-defined-types"></a>Dekonstruieren von benutzerdefinierten Typen

Jeder Tupeltyp kann dekonstruiert werden, wie oben gezeigt wurde. Es ist genau so einfach, die Dekonstruktion in beliebigen benutzerdefinierten Typen (Klassen, Strukturen oder sogar Oberflächen) zu aktivieren.

Der Autor des Typs kann eine oder mehrere `Deconstruct`-Methoden definieren, die einer beliebigen Anzahl von [`out`-Variablen](language-reference/keywords/out-parameter-modifier.md) Werte zuweisen, die die Datenelemente darstellen, die den Typ ausmachen. Der folgende `Person`-Typ definiert z.B. eine `Deconstruct`-Methode, die ein Personenobjekt in die Elemente dekonstruiert, die dem Vor- und Nachnamen entsprechen:

[!code-csharp[TypeWithDeconstructMethod](../../samples/snippets/csharp/tuples/person.cs#12_TypeWithDeconstructMethod "Type with a deconstruct method")]

Die Dekonstruktionsmethode ermöglicht die Zuordnung von einer `Person` zu zwei Zeichenfolgen, die die Eigenschaften `FirstName` und `LastName` darstellen:

[!code-csharp[Deconstruct Type](../../samples/snippets/csharp/tuples/program.cs#12A_DeconstructType "Deconstruct a class type")]

Sie können Dekonstruktion selbst für Typen aktivieren, die Sie nicht geschrieben haben.
Die `Deconstruct`-Methode kann eine Erweiterungsmethode sein, die die zugänglichen Datenmember eines Objekts entpackt. Das folgende Beispiel zeigt einen `Student`-Typ, der vom `Person`-Typ abgeleitet wurde, sowie eine Erweiterungsmethode, die ein `Student` in drei Variablen dekonstruiert, die den `FirstName`, `LastName` und `GPA` darstellen:

[!code-csharp[ExtensionDeconstructMethod](../../samples/snippets/csharp/tuples/person.cs#13_ExtensionDeconstructMethod "Type with a deconstruct extension method")]

Ein `Student`-Objekt hat jetzt zwei zugängliche `Deconstruct`-Methoden: Die Erweiterungsmethode, die für `Student`-Typen deklariert wurde, und die Member des `Person`-Typs. Beide befinden sich im Geltungsbereich, womit ein `Student` entweder in zwei oder drei Variablen dekonstruiert werden kann.
Wenn Sie einem Studenten drei Variablen zuweisen, werden der Vorname, der Nachname sowie das GPA zurückgegeben. Wenn Sie einem Studenten zwei Variablen zuweisen, werden nur Vor- und Nachname zurückgegeben.

[!code-csharp[Deconstruct extension method](../../samples/snippets/csharp/tuples/program.cs#13A_DeconstructExtension "Deconstruct a class type using an extension method")]

Sie sollten vorsichtig mit dem Definieren von mehreren `Deconstruct`-Methoden in einer Klasse oder einer Klassenhierarchie sein. Mehrere `Deconstruct`-Methoden, die die gleiche Anzahl von `out`-Parameter haben, können schnell zu Mehrdeutigkeiten führen. Aufrufer können dann vielleicht nicht die gewünschte `Deconstruct`-Methode aufrufen.

In diesem Beispiel besteht eine minimale Wahrscheinlichkeit für einen mehrdeutigen Aufruf, weil die `Deconstruct`-Methode für `Person` zwei Ausgabeparameter besitzt, und die `Deconstruct`-Methode für `Student` drei besitzt.

Dekonstruktionsoperatoren werden nicht für Gleichheitstests verwendet. Das folgende Beispiel generiert den Compilerfehler CS0019:

```csharp
Person p = new Person("Althea", "Goodwin");
if (("Althea", "Goodwin") == p)
    Console.WriteLine(p);
```

Die Methode `Deconstruct` kann das `Person`-Objekt `p` in ein Tupel konvertieren, das zwei Zeichenfolgen enthält. Dieses gilt jedoch nicht im Kontext von Gleichheitstests.

## <a name="tuples-as-out-parameters"></a>Tupel als out-Parameter

Tupel können *selbst* als [`out`-Parameter](language-reference/keywords/out-parameter-modifier.md) verwendet werden. Dies sollte nicht mit einer Mehrdeutigkeit verwechselt werden, die zuvor im Abschnitt [Dekonstruktion ](#deconstruction) erwähnt wurde. In einem Methodenaufruf müssen Sie nur die Form des Tupels beschreiben:

[!code-csharp[TuplesAsOutParameters](~/samples/snippets/csharp/tuples/program.cs#01_TupleAsOutVariable "Tuples as out parameters")]

Alternativ können Sie ein [_unbenanntes_](#named-and-unnamed-tuples) Tupel verwenden und auf seine Felder als `Item1` und `Item2` verweisen:

```csharp
dict.TryGetValue(2, out (int, string) pair);
// ...
Console.WriteLine($"{pair.Item1}: {pair.Item2}");
```

## <a name="conclusion"></a>Schlussbemerkung

Die neue Sprach- und Bibliotheksunterstützung für benannte Tupel vereinfacht es, mit Entwürfen zu arbeiten, die Datenstrukturen verwenden, die mehrere Elemente definieren, aber keine Verhalten definieren, wie es Klassen und Strukturen tun. Die Verwendung von Tupeln ist für diese Typen einfach und präzise. Sie erhalten alle Vorteile der Überprüfung von statischen Typen, ohne Typen mithilfe der ausführlicheren `class`- oder `struct`-Syntax schreiben zu müssen. Dennoch sind sie für Hilfsmethoden, die `private` oder `internal` sind, am nützlichsten. Erstellen Sie benutzerdefinierte Typen, entweder `class` oder `struct`, wenn Ihre öffentlichen Methoden einen Wert mit mehreren Elementen zurückgeben.
