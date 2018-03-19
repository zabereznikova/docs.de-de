---
title: "Neues in C# 7 – Leitfaden für C#"
description: "Erhalten Sie einen Überblick über die neuen Funktionen in der bevorstehenden Version 7 der C#-Sprache."
keywords: C#, .NET, .NET Core, neueste Funktionen, Neues
author: BillWagner
ms.author: wiwagn
ms.date: 12/21/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 374ac9917464a7e83566440abab10eda8a9c8683
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="whats-new-in-c-7"></a>Neues in C# 7

C# 7 bietet eine Reihe von neuen Funktionen für die C#-Sprache:
* [`out`Variablen](#out-variables)
    - Sie können `out`-Werte inline als Argumente für die Methode deklarieren, wenn sie verwendet werden.
* [Tupel](#tuples)
    - Sie können einfache, unbenannte Typen erstellen, die mehrere öffentliche Felder enthalten. Compiler und IDE-Tools kennen die Semantik dieser Typen.
* [Verwerfen](#discards)
    - Ausschussvariablen (discards) sind temporäre, lesegeschützte Variablen, die in Zuweisungen verwendet werden, wenn der zugewiesene Wert nicht weiter interessiert. Sie sind besonders zum Dekonstruieren von Tupeln und benutzerdefinierten Typen sowie beim Aufrufen von Methoden mit `out`-Parametern nützlich.
* [Mustervergleich](#pattern-matching)
    - Sie können Verzweigungslogik basierend auf beliebigen Typen und Werten der Member dieser Typen erstellen.
* [Lokale `ref`-Variablen und Rückgabetypen](#ref-locals-and-returns)
    - Methodenargumente und lokale Variablen können Verweise auf andere Speicher sein.
* [Lokale Funktionen](#local-functions)
    - Sie können Funktionen innerhalb von anderen Funktionen verschachteln, um deren Bereich und Sichtbarkeit zu beschränken.
* [Mehr Ausdruckskörpermember](#more-expression-bodied-members)
    - Die Liste der Member, die mithilfe von Ausdrücken erstellt werden können, ist länger geworden.
* [`throw`-Ausdrücke](#throw-expressions)
    - Sie können Ausnahmen in Codekonstrukten auslösen, die vorher nicht zulässig waren, da `throw` eine Anweisung war. 
* [Generalisierte asynchrone Rückgabetypen](#generalized-async-return-types)
    - Methoden, die mit dem `async`-Modifizierer deklariert werden, können zusätzlich zu `Task` und `Task<T>` andere Typen zurückgeben.
* [Verbesserung der numerischen literalen Syntax](#numeric-literal-syntax-improvements)
    - Neue Token verbessern die Lesbarkeit für numerische Konstanten.

Im weiteren Verlauf dieses Themas werden die einzelnen Funktionen erläutert. Sie werden die Hintergründe jeder einzelnen Funktion erfahren. Sie werden die Syntax erlernen. Sie werden einige Beispielszenarios sehen, in denen die neue Funktion Sie als Entwickler produktiver macht. 

## <a name="out-variables"></a>`out`-Variablen

Die vorhandene Syntax zur Unterstützung von `out`-Parametern wurde in dieser Version verbessert.  

Bisher mussten Sie die Deklaration der out-Variablen und ihre Initialisierung in zwei verschiedene Anweisungen trennen:

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

Nun können Sie `out`-Variablen in der Argumentliste eines Methodenaufrufs deklarieren, anstatt eine separate Deklarationsanweisung zu schreiben:

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

Möglicherweise möchten Sie den Typ der `out`-Variablen aus Gründen der Übersichtlichkeit angeben, wie oben gezeigt. Die Sprache unterstützt jedoch die Verwendung einer implizit typisierten lokalen Variable:

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* Der Code ist einfacher zu lesen. 
    - Sie deklarieren die out-Variable, wenn Sie sie verwenden, nicht in einer anderen Zeile weiter oben.
* Sie müssen keinen Anfangswert zuweisen.
    - Durch das Deklarieren der `out`-Variable, wenn sie in einem Methodenaufruf verwendet wird, können Sie sie nicht versehentlich verwenden, bevor sie zugewiesen wurde.

Die häufigste Verwendung dieser Funktion ist das `Try`-Muster. In diesem Muster gibt eine Methode ein `bool` zurück, das Erfolg oder Misserfolg angibt, sowie eine `out`-Variable, die das Ergebnis enthält, wenn die Methode erfolgreich ist.

Bei Verwendung der `out`-Variablendeklaration „sickert“ die deklarierte Variable in den äußeren Bereich der if-Anweisung. Dadurch können Sie die Variable anschließend verwenden:

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a>Tupel

> [!NOTE]
> Die neuen Tupeleigenschaften benötigen die <xref:System.ValueTuple>-Typen.
> Sie müssen das NuGet-Paket [ `System.ValueTuple` ](https://www.nuget.org/packages/System.ValueTuple/) hinzufügen, um es auf Plattformen zu verwenden, die keine Typen enthalten.
>
> Dies ist ähnlich wie bei anderen Sprachfunktionen, die auf im Framework übermittelten Typen basieren. Beispiele hierfür sind `async` und `await`, die auf der `INotifyCompletion`-Schnittstelle basieren, und LINQ, das auf `IEnumerable<T>` basiert. Allerdings ändert sich der Übermittlungsmechanismus, da .NET plattformunabhängiger wird. .NET Framework wird möglicherweise nicht immer im gleichen Rhythmus wie der Sprachcompiler ausgeliefert. Wenn neue Sprachfunktionen auf neuen Typen basieren, sind diese Typen als NuGet-Pakete bei der Auslieferung der Sprachfunktionen verfügbar. Da diese neuen Typen dem standardmäßigen .NET API hinzugefügt und als Teil des Frameworks bereitgestellt werden, wird die Anforderung des NuGet-Pakets entfernt.

C# bietet eine umfangreiche Syntax für Klassen und Strukturen, die verwendet wird, um Ihre Entwurfsabsicht zu erläutern. Aber manchmal erfordert diese umfangreiche Syntax zusätzliche Arbeit mit minimalem Nutzen. Möglicherweise schreiben Sie häufig Methoden, die eine einfache Struktur erfordern, die mehr als ein Datenelement enthält. Zur Unterstützung dieser Szenarios wurden C# *Tupel* hinzugefügt. Tupel sind einfache Datenstrukturen, die mehrere Felder zur Darstellung der Datenmember enthalten.
Die Felder werden nicht überprüft, und Sie können keine eigenen Methoden definieren

> [!NOTE]
> Tupel waren schon vor C# 7 verfügbar, sie waren jedoch ineffizient und hatten keine Sprachunterstützung.
> Das brachte mit sich, dass auf Tupelelemente nur als `Item1`, `Item2` usw. verwiesen werden konnte. Mit C# 7 wird Sprachunterstützung für Tupel eingeführt, wodurch semantische Namen für die Felder eines Tupels mit Einsatz neuer, effizienterer Tupeltypen möglich werden.

Sie können ein Tupel erstellen, indem Sie jeden Member einem Wert zuweisen:

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

Durch diese Zuweisung wird ein Tupel erstellt, dessen Elemente `Item1` und `Item2` sind, die Sie in der gleichen Weise wie <xref:System.Tuple> verwenden können. Sie können die Syntax ändern, um ein Tupel zu erstellen, das jedem der Elemente des Tupels einen semantischen Namen verleiht:

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

Das `namedLetters`-Tupel enthält Felder, die als `Alpha` und `Beta` bezeichnet werden. Diese Namen bestehen nur zur Kompilierzeit und werden nicht beibehalten, wenn das Tupel beispielsweise zur Laufzeit mithilfe von Reflektion untersucht wird.

In einer Tupelzuweisung können Sie auch die Namen der Felder auf der rechten Seite der Zuweisung angeben:

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

Sie können Namen für die Felder auf der linken und rechten Seite der Zuweisung angeben:

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

Die Zeile oben generiert eine Warnung `CS8123`, die angibt, dass die Namen `Alpha` und `Beta` auf der rechten Seite der Zuweisung ignoriert werden, da sie mit den Namen `First` und `Second` auf der linken Seite im Konflikt stehen.

Die Beispiele oben zeigen die grundlegende Syntax zum Deklarieren von Tupeln. Tupel sind am nützlichsten als Rückgabetypen für `private`- und `internal`-Methoden. Tupel bieten eine einfache Syntax für diese Methoden, um mehrere diskrete Werte zurückzugeben: Sie sparen sich die Arbeit, ein `class` oder ein `struct` zu erstellen, das den zurückgegebenen Typ definiert. Es ist nicht erforderlich, einen neuen Typ zu erstellen.

Ein Tupel zu erstellen, ist effizienter und produktiver.
Es ist eine einfachere Syntax, um eine Datenstruktur mit mehr als einem Wert zu definieren. Die folgende Beispielmethode gibt die minimalen und maximalen Werte in einer Sequenz von ganzen Zahlen zurück:

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

Tupel auf diese Weise zu verwenden, bietet mehrere Vorteile:

* Sie sparen sich die Arbeit, ein `class` oder ein `struct` zu erstellen, das den zurückgegebenen Typ definiert. 
* Sie müssen keinen neuen Typ erstellen.
* Die Verbesserungen der Sprache beseitigen die Notwendigkeit, die <xref:System.Tuple.Create``1(``0)>-Methoden aufzurufen.

Die Deklaration der Methode liefert die Namen für die Felder des Tupels, das zurückgegeben wird. Wenn Sie die Methode aufrufen, ist der Rückgabewert ein Tupel mit den Feldern `Max` und `Min`:

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

Manchmal möchten Sie vielleicht die Member eines Tupels entpacken, die von einer Methode zurückgegeben wurden.  Sie können dazu für jeden Wert im Tupel separate Variablen deklarieren. Dies wird als *Dekonstruieren* des Tupels bezeichnet:

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

<!-- Add wildcards here, if they are in C# 7
-->

Sie können auch eine ähnliche Dekonstruktion für alle Typen in .NET bereitstellen. Dies erfolgt durch das Schreiben einer `Deconstruct`-Methode als Member der Klasse. Diese `Deconstruct`-Methode bietet eine Reihe von `out`-Argumenten für jede der Eigenschaften, die Sie extrahieren möchten. Berücksichtigen Sie diese `Point`-Klasse, die eine Dekonstruktionsmethode bereitstellt, die die `X`- und `Y`-Koordinaten extrahiert:

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
Sie können die einzelnen Felder extrahieren, indem Sie ein Tupel einem `Point` zuweisen:

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

Sie sind nicht an die Namen gebunden, die in der `Deconstruct`-Methode definiert sind. Sie können die extrahierten Variablen als Teil der Zuweisung umbenennen:  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

Ausführliche Informationen zu Tupeln erhalten Sie unter [tuples topic (Thema „Tupel“)](../tuples.md).

## <a name="discards"></a>Ausschuss

Beim Dekonstruieren eines Tupels oder dem Aufrufen einer Methode mit `out`-Parametern sind Sie gezwungen, eine Variable zu definieren, deren Wert Sie nicht interessiert und die Sie nicht zu verwenden beabsichtigen. C# verfügt jetzt über Unterstützung für *Ausschussvariablen* (discards), um diesem Szenario Rechnung zu tragen. Eine Ausschussvariable ist eine lesegeschützte Variable mit dem Namen `_` (dem Unterstrichzeichen); Sie können der einzelnen Variablen alle Werte zuweisen, die Sie verwerfen möchten. Eine Ausschussvariable ist wie eine nicht zugewiesene Variable; abgesehen von der Zuweisungsanweisung kann die Ausschussvariable nicht in Code verwendet werden.

Ausschussvariablen werden in den folgenden Szenarien unterstützt:

* Beim Dekonstruieren von Tupeln oder benutzerdefinierten Typen.

* Beim Aufrufen von Methoden mit [out](../language-reference/keywords/out-parameter-modifier.md)-Parametern.

* In einem Musterabgleichsvorgang mit den Anweisungen [is](../language-reference/keywords/is.md) und [switch](../language-reference/keywords/switch.md).

* Als eigenständiger Bezeichner, wenn Sie den Wert einer Zuweisung explizit als Ausschuss kennzeichnen möchten.

Das folgende Beispiel definiert eine `QueryCityDataForYears`-Methode, die ein 6-Tupel zurückgibt, das ein Datum für eine Stadt für zwei verschiedene Jahre enthält. Der Methodenaufruf im Beispiel befasst sich nur mit den zwei Bevölkerungswerten, die von der Methode zurückgegeben werden und behandelt so die verbleibenden Werte im Tupel beim Dekonstruieren des Tupels als Ausschuss.

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Weitere Informationen finden Sie unter [Ausschuss](../discards.md).
 
## <a name="pattern-matching"></a>Musterabgleich

*Mustervergleich* ist ein Funktion, mit der Sie Methodenverteilung für andere Eigenschaften als den Typ eines Objekts implementieren können. Sie sind wahrscheinlich bereits vertraut mit Methodenverteilung, die auf dem Typ eines Objekts basiert. In der objektorientierten Programmierung bieten virtuelle und Überschreibungsmethoden Sprachsyntax, um Methodenverteilung basierend auf dem Typ eines Objekts zu implementieren. Basis- und abgeleitete Klassen stellen verschiedene Implementierungen bereit. Mustervergleichsausdrücke erweitern dieses Konzept, sodass Sie ähnliche Verteilungsmuster für Typen und Datenelemente, die nicht durch eine Vererbungshierarchie verknüpft sind, einfach implementieren können. 

Mustervergleich unterstützt `is`-Ausdrücke und `switch`-Ausdrücke. Jeder davon ermöglicht das Überprüfen eines Objekts und dessen Eigenschaften, um zu bestimmen, ob das Objekt dem gesuchten Muster entspricht. Sie verwenden das `when`-Schlüsselwort, um zusätzliche Regeln für das Muster anzugeben.

### <a name="is-expression"></a>`is`-Ausdruck

Der Musterausdruck `is` erweitert den vertrauten `is`-Operator auf das Abfragen eines Objekts über den Typ hinaus.

Beginnen wir mit einem einfachen Szenario. Wir fügen Funktionen für dieses Szenario hinzu, die veranschaulichen, wie Mustervergleichsausdrücke Algorithmen erstellen, die mit nicht verknüpften Typen einfach funktionieren. Wir beginnen mit einer Methode, die die Summe aller gewürfelten Augen bei mehreren Würfelvorgängen berechnet:

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

Sie werden möglicherweise schnell feststellen, dass Sie die Summe von gewürfelten Augen ermitteln müssen, wenn einige Würfelvorgänge mit mehreren Würfeln ausgeführt werden. Ein Teil der Eingabesequenz kann aus mehreren Ergebnissen anstatt einer einzelnen Zahl bestehen:

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

Der `is`-Ausdruck des Musters funktioniert in diesem Szenario sehr gut. Als Teil der Überprüfung des Typ schreiben Sie eine Variableninitialisierung. Dadurch wird eine neue Variable des validierten Laufzeittyps erstellt.

Wenn Sie diese Szenarios erweitern, werden Sie möglicherweise feststellen, dass Sie mehr `if`- und `else if`-Anweisungen erstellen. Sobald dies unhandlich wird, möchten Sie wahrscheinlich zu `switch`-Ausdrücken des Musters wechseln.

### <a name="switch-statement-updates"></a>Aktualisierungen der `switch`-Anweisung

Der *Vergleichsausdruck* verfügt über eine vertraute Syntax, die auf der `switch`-Anweisung basiert, die bereits Teil der C#-Sprache ist. Übersetzen wir den vorhandenen Code, um vor dem Hinzufügen neuer Fälle einen Vergleichsausdruck zu verwenden: 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

Die Vergleichsausdrücke haben eine etwas andere Syntax als die `is`-Ausdrücke, bei denen Sie den Typ und die Variable am Anfang des `case`-Ausdrucks deklarieren.

Die Vergleichsausdrücke unterstützen auch Konstanten. Dies kann durch das Ausklammern von einfachen Fällen Zeit sparen:

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

Der obige Code fügt Fälle für `0` als Sonderfall von `int` hinzu und `null` als besonderen Fall, wenn keine Eingabe vorhanden ist. Hierdurch wird eine wichtige neue Funktion in switch-Musterausdrücken veranschaulicht: Die Reihenfolge der `case`-Ausdrücke ist nun von Bedeutung. Der `0`-Fall muss vor dem allgemeinen `int`-Fall erscheinen. Andernfalls wäre das erste zu vergleichende Muster der `int`-Fall, auch wenn der Wert `0` ist. Wenn Sie Vergleichsausdrücke aus Versehen so sortieren, dass ein späterer Fall bereits behandelt wurde, wird der Compiler dies kennzeichnen und einen Fehler generieren.

Dieses Verhalten aktiviert den Sonderfall für eine leere Eingabesequenz.
Sie sehen, dass der Fall für ein `IEnumerable`-Element mit Elementen vor dem allgemeinen `IEnumerable`-Fall erscheinen muss.

In dieser Version wurde ebenfalls ein `default`-Fall hinzugefügt. Der `default`-Fall wird immer zuletzt ausgewertet, unabhängig von der Reihenfolge, in der er in der Quelle erscheint. Aus diesem Grund ist es üblich, den `default`-Fall ans Ende zu stellen.

Abschließend fügen wir einen letzten `case` für eine neue Art von Würfel hinzu. Einige Spiele verwenden Prozentwürfel, um größere Bereiche von Zahlen darzustellen. 

> [!NOTE]
> Zwei 10-seitige Prozentwürfel können jede Zahl von 0 bis 99 darstellen. Die Seiten des einen Würfels haben die Bezeichnungen `00`, `10`, `20`,... `90`. Die Seiten des anderen Würfels haben die Bezeichnungen `0`, `1`, `2`,... `9`. Wenn Sie die Werte der beiden Würfel addieren, können Sie jede Zahl von 0 bis 99 erhalten.

Um Ihrer Sammlung diese Art von Würfel hinzuzufügen, müssen Sie zunächst einen Typ zur Darstellung des Prozentwürfels definieren. Die `TensDigit` Eigenschaft speichert die Werte `0`, `10`, `20` bis zu `90`:

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

Fügen Sie dann einen `case`-Vergleichsausdruck für den neuen Typ hinzu:

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

Die neue Syntax für Mustervergleichsausdrücke erleichtert das Erstellen von Verteilungsalgorithmen auf der Basis des Typs eines Objekts oder anderen Eigenschaften mit einer klaren und präzisen Syntax. Mustervergleichsausdrücke ermöglichen diese Konstrukte auf Datentypen, die durch Vererbung nicht verbunden sind.

Weitere Informationen zum Mustervergleich finden Sie im Thema [pattern matching in C# (Mustervergleich in (C#))](../pattern-matching.md).

## <a name="ref-locals-and-returns"></a>Lokale ref-Variablen und Rückgabetypen

Diese Funktion ermöglicht Algorithmen, die Verweise auf Variablen verwenden und zurückgeben, die an anderer Stelle definiert sind. Ein Beispiel ist das Arbeiten mit großen Matrizen und die Suche nach einem einzigen Ort mit bestimmten Eigenschaften. Eine Methode würde die zwei Indizes für einen einzigen Speicherort in der Matrix zurückgeben:

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

Es gibt viele Probleme mit diesem Code. Zunächst einmal handelt es sich um eine öffentliche Methode, die ein Tupel zurückgibt. Die Sprache unterstützt dies, aber benutzerdefinierte Typen (Klassen oder Strukturen) werden für öffentliche APIs bevorzugt.

Zweitens gibt diese Methode die Indizes an das Element in der Matrix zurück.
Daraus ergibt sich, dass Aufrufer Code schreiben, der mit diesen Indizes die Matrix dereferenziert und ein einzelnes Element ändert:

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

Sie würden eher eine Methode schreiben, die einen *Verweis* auf das Element der Matrix zurückgibt, die Sie ändern möchten. Dies konnten Sie in früheren Versionen nur durch Verwenden von unsicherem Code und Rückgabe eines Zeigers auf eine `int` erreichen.

Betrachten wir nun eine Reihe von Änderungen, um die lokale ref-Funktion zu präsentieren und zu zeigen, wie Sie eine Methode erstellen, die einen Verweis auf den internen Speicher zurückgibt.
Nebenbei erfahren Sie die Regeln der ref-Rückgabe und der lokalen ref-Funktion, um zu verhindern, dass Sie sie versehentlich falsch verwenden.

Ändern Sie zuerst die `Find`-Methodendeklaration, sodass sie eine `ref int` anstelle eines Tupels zurückgibt. Ändern Sie dann die return-Anweisung, sodass sie den in der Matrix gespeicherten Wert anstatt der zwei Indizes zurückgibt:

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

Wenn Sie deklarieren, dass eine Methode eine `ref`-Variable zurückgibt, müssen Sie auch das `ref`-Schlüsselwort zu jeder return-Anweisung hinzufügen. So wird die Rückgabe durch Verweis angegeben, sodass Entwickler später beim Lesen des Codes wissen, dass die Methode durch Verweis zurückgibt:

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

Nun gibt die Methode einen Verweis auf den ganzzahligen Wert in der Matrix zurück, und Sie müssen ändern, wo sie aufgerufen wird.  Die `var`-Deklaration bedeutet, dass `valItem` jetzt eine `int` anstatt ein Tupel ist:

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

Die zweite `WriteLine`-Anweisung im obigen Beispiel gibt den Wert `42` aus und nicht `24`. Die Variable `valItem` ist eine `int` und nicht eine `ref int`. Durch das `var`-Schlüsselwort kann der Compiler den Typ angeben, fügt jedoch nicht implizit den `ref`-Modifizierer hinzu. Stattdessen wird der Wert, auf den `ref return` verweist, an die Variable auf der linken Seite der Zuweisung *kopiert*. Die Variable ist keine lokale `ref`.

Um das gewünschte Ergebnis zu erhalten, müssen Sie den `ref`-Modifizierer der Deklaration der lokalen Variablen hinzufügen, um aus der Variablen einen Verweis herzustellen, wenn der Rückgabewert ein Verweis ist:

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

Nun gibt die zweite `WriteLine`-Anweisung im obigen Beispiel den Wert `24` aus, der angibt, dass der Speicher in der Matrix geändert wurde. Die lokale Variable wurde mit dem `ref`-Modifizierer deklariert und nimmt eine `ref`-Rückgabe an. Sie müssen eine `ref`-Variable initialisieren, wenn sie deklariert wird, und können Deklaration und Initialisierung nicht trennen.

Die C#-Sprache verfügt über drei weitere Regeln, die Sie vor der falschen Verwendung der lokalen `ref`-Variablen und Rückgaben schützen:

* Sie können einer lokalen `ref`-Variablen keinen Standard-Methodenrückgabewert zuweisen.
    - Dadurch werden Aussagen wie `ref int i = sequence.Count();` nicht zugelassen.
* Sie können eine `ref` nicht an eine Variable zurückgeben, deren Lebensdauer sich nicht über die Ausführung der Methode hinaus erstreckt.
    - Das bedeutet, dass Sie keinen Verweis auf eine lokale Variable oder eine Variable mit einem ähnlichen Bereich zurückgeben können.
* Lokale `ref`-Variablen und Rückgabewerte können nicht in Verbindung mit asynchronen Methoden verwendet werden.
    - Der Compiler kann nicht feststellen, ob die Variable, auf die verwiesen wird, bei der Rückgabe der asynchronen Methode auf ihren endgültigen Wert festgelegt ist.

Das Hinzufügen von lokalen ref-Variablen und ref-Rückgaben ermöglicht effizientere Algorithmen, da Werte nicht kopiert und dereferenzierende Vorgänge nicht mehrmals ausgeführt werden. 

## <a name="local-functions"></a>Lokale Funktionen

Viele Entwürfe für Klassen enthalten Methoden, die nur von einer Stelle aufgerufen werden. Durch diese zusätzlichen privaten Methoden bleibt jede Methode klein und konzentriert. Allerdings können Sie das Verstehen einer Klasse beim ersten Lesen erschweren. Diese Methoden müssen außerhalb des Kontexts des einzelnen Aufruforts verstanden werden.

Für diese Entwürfe ermöglichen *lokale Funktionen*, Methoden innerhalb des Kontexts einer anderen Methode zu deklarieren. So können Leser der Klasse leichter erkennen, dass die lokale Methode nur aus dem Kontext aufgerufen wird, in dem sie deklariert ist.

Es gibt zwei sehr häufige Anwendungsfälle für lokale Funktionen: öffentliche Iteratormethoden und öffentliche asynchrone Methoden. Beide Arten von Methoden generieren Code, der Fehler später meldet, als Programmierer erwarten würden. Bei Iteratormethoden werden Ausnahmen nur festgestellt, wenn Code aufgerufen wird, der die zurückgegebene Sequenz auflistet. Bei asynchronen Methoden werden Ausnahmen nur festgestellt, wenn der zurückgegebene `Task` erwartet wird.

Beginnen wir mit einer Iteratormethode:

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

Betrachten Sie den folgenden Code, der die Iteratormethode falsch aufruft:

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

Die Ausnahme wird ausgelöst, wenn `resultSet` iteriert wird, nicht wenn `resultSet` erstellt wird.
In diesem Beispiel könnten die meisten Entwickler das Problem schnell diagnostizieren. In größeren Codebasen befindet sich der Code, der einen Iterator erstellt, jedoch häufig nicht so nah an dem Code, der das Ergebnis auflistet. Sie können den Code so umgestalten, dass die öffentliche Methode alle Argumente überprüft und eine private Methode die Enumeration generiert:

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

Diese umgestaltete Version löst Ausnahmen sofort aus, da die öffentliche Methode keine Iteratormethode ist; nur die private Methode verwendet die `yield return`-Syntax. Es gibt bei dieser Umgestaltung allerdings potenzielle Probleme. Die private Methode sollte nur von der öffentlichen Schnittstellenmethode aufgerufen werden, da sonst jegliche Argumentüberprüfung übersprungen wird.
Leser der Klasse müssen diese Tatsache ermitteln, indem Sie die gesamte Klasse lesen und auf andere Verweise auf die `alphabetSubsetImplementation`-Methode durchsuchen.

Sie können diese Entwurfsabsicht deutlicher machen, indem Sie die `alphabetSubsetImplementation` als lokale Funktion innerhalb der öffentlichen API-Methode deklarieren:

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

Die obige Version macht deutlich, dass auf die lokale Methode nur im Kontext der äußeren Methode verwiesen wird. Die Regeln für lokale Funktionen stellen auch sicher, dass ein Entwickler nicht versehentlich die lokale Funktion von einem anderen Speicherort in der Klasse aufrufen und die Argumentüberprüfung umgehen kann.

Das gleiche Verfahren kann mit `async`-Methoden eingesetzt werden, um sicherzustellen, dass Ausnahmen aufgrund der Argumentüberprüfung ausgelöst werden, bevor die asynchrone Arbeit beginnt:

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> Einige der Entwürfe, die von lokalen Funktionen unterstützt werden, könnten auch mithilfe von *Lambdaausdrücken* erreicht werden. Interessierte Benutzer können [mehr über die Unterschiede erfahren](../local-functions-vs-lambdas.md).

## <a name="more-expression-bodied-members"></a>Mehr Ausdruckskörpermember

In C# 6 wurden [Ausdruckskörpermember](csharp-6.md#expression-bodied-function-members) für Memberfunktionen und schreibgeschützte Eigenschaften eingeführt. C# 7 erweitert die zulässigen Member, die als Ausdrücke implementiert werden können. In C# 7 können Sie *Konstruktoren*, *Finalizer* sowie `get`- und `set`-Zugriffsmethoden für *Eigenschaften* und *Indexer* implementieren. Der folgende Code zeigt entsprechende Beispiele:

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> In diesem Beispiel ist kein Finalizer erforderlich, aber damit soll die Syntax dargestellt werden. Sie sollten in Ihrer Klasse nur einen Finalizer implementieren, wenn es notwendig ist, nicht verwaltete Ressourcen freizugeben. Sie sollten auch die Verwendung der <xref:System.Runtime.InteropServices.SafeHandle>-Klasse in Betracht ziehen, anstatt nicht verwaltete Ressourcen direkt zu verwalten.

Diese neuen Speicherorte für Ausdruckskörpermember sind ein wichtiger Meilenstein für C#: Diese Funktionen wurden von Community-Mitgliedern implementiert, die am Open-Source-Projekt [Roslyn](https://github.com/dotnet/Roslyn) arbeiten.

## <a name="throw-expressions"></a>Throw-Ausdrücke

In C# ist `throw` schon immer eine Anweisung. Da `throw` eine Anweisung und kein Ausdruck ist, gab es C#-Konstrukte, in denen diese nicht verwendet werden konnte. Darunter waren bedingte Ausdrücke, NULL-Sammelausdrücke und einige Lambdaausdrücke. Das Hinzufügen von Ausdruckskörpermembern fügt mehr Speicherorte hinzu, bei denen `throw`-Ausdrücke nützlich wären. Damit Sie diese Konstrukte schreiben können, führt C# 7 *Throw-Ausdrücke* ein.

Die Syntax ist dieselbe, die Sie für `throw`-Anweisungen immer verwendet haben. Der einzige Unterschied ist, dass sie nun an neuen Speicherorten wie z.B. in einem bedingten Ausdruck platziert werden können:

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

Diese Funktion ermöglicht das Verwenden von Throw-Ausdrücken in Initialisierungsausdrücken:

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

Bisher mussten sich diese Initialisierungen in einem Konstruktor und die Throw-Anweisungen im Text des Konstruktors befinden :


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> Beide vorhergehenden Konstrukte lösen Ausnahmen während der Erstellung eines Objekts aus. Diese sind oft schwierig zu beheben.
> Aus diesem Grund sind Entwürfe, die Ausnahmen während der Erstellung auslösen, nicht empfehlenswert.

## <a name="generalized-async-return-types"></a>Generalisierte asynchrone Rückgabetypen

Das Zurückgeben eines `Task`-Objekts von asynchronen Methoden kann Leistungsengpässe in bestimmten Pfaden verursachen. `Task` ist ein Verweistyp, seine Verwendung bedeutet also das Zuordnen eines Objekts. In Fällen, in denen eine mit dem `async`-Modifizierer deklarierte Methode ein zwischengespeichertes Ergebnis zurückgibt oder synchron abschließt, können die zusätzlichen Zuordnungen viel Zeit bei der Ausführung kritischer Codeabschnitte kosten. Es kann sehr kostspielig werden, wenn diese Zuordnungen in engen Schleifen auftreten.

Die neue Sprachfunktion bedeutet, dass asynchrone Methoden zusätzlich zu `Task`, `Task<T>` und `void` andere Typen zurückgeben können. Der zurückgegebene Typ muss noch immer das asynchrone Muster erfüllen, d.h. dass eine `GetAwaiter`-Methode verfügbar sein muss. Als konkretes Beispiel wurde der `ValueTask`-Typ zu .NET Framework hinzugefügt, um diese neue Sprachfunktion zu nutzen: 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> Sie müssen das NuGet-Paket hinzufügen [ `System.Threading.Tasks.Extensions` ](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/), um den Typ <xref:System.Threading.Tasks.ValueTask%601> verwenden zu können.

Eine einfache Optimierung wäre es, `ValueTask` da zu verwenden, wo zuvor `Task` verwendet wurde. Wenn Sie jedoch zusätzliche Optimierungen manuell ausführen möchten, können Sie Ergebnisse asynchroner Arbeit zwischenspeichern und bei späteren Aufrufen wiederverwenden. Die `ValueTask`-Struktur verfügt über einen Konstruktor mit einem `Task`-Parameter, sodass Sie einen `ValueTask` aus dem Rückgabewert einer beliebigen vorhandenen asynchronen Methode konstruieren können:

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]
 
Wie bei allen Leistungsempfehlungen sollte Sie für beide Versionen einen Vergleichstest durchführen, bevor Sie an Ihrem Code große Veränderungen vornehmen.

## <a name="numeric-literal-syntax-improvements"></a>Verbesserung der numerischen literalen Syntax

Falsches Lesen numerischer Konstanten kann Code beim ersten Lesen schwerer verständlich machen. Dies tritt häufig auf, wenn diese Zahlen als Bitmasken oder als andere symbolische und nicht numerische Werte verwendet werden. C# 7 enthält zwei neue Funktionen, um das Schreiben von Zahlen für den beabsichtigten Zweck übersichtlicher zu machen: *Binäre Literale* und *Trennzeichen für Ziffern*.

Bei der Erstellung von Bitmasken oder wenn eine binäre Darstellung einer Zahl den Code besonders gut lesbar macht, sollten Sie diese Zahl im Binärformat schreiben:

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

Das `0b` am Anfang der Konstante gibt an, dass die Zahl als binäre Zahl geschrieben wird.

Binäre Zahlen können sehr lang werden, daher kann die Einführung des `_` als Zifferntrennzeichen die Bitmuster übersichtlicher machen:

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

Das Zifferntrennzeichen kann überall in der Konstante angezeigt werden. Für Zahlen der Basis 10 wäre es üblich, es als Tausendertrennzeichen zu verwenden:

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

Das Zifferntrennzeichen kann auch mit den Typen `decimal`, `float` und `double` verwendet werden:

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

Insgesamt können Sie numerische Konstanten viel leserlicher deklarieren.
