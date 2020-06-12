---
title: Neues in C# 7.0 – C#-Leitfaden
description: Erhalten Sie einen Überblick über die neuen Funktionen in Version 7.0 der C#-Sprache.
ms.date: 02/20/2019
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: e78d680e19709bf3dd854531d5d9f6b7d6464f49
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392248"
---
# <a name="whats-new-in-c-70"></a>Neues in C# 7.0

C# 7.0 bietet eine Reihe von neuen Features für die C#-Programmiersprache:

- [`out`Variablen](#out-variables)
  - Sie können `out`-Werte als Inlineargumente für die Methode deklarieren, wenn sie verwendet werden.
- [Tupel](#tuples)
  - Sie können einfache, unbenannte Typen erstellen, die mehrere öffentliche Felder enthalten. Compiler und IDE-Tools kennen die Semantik dieser Typen.
- [Verwerfen](#discards)
  - Ausschussvariablen (discards) sind temporäre, lesegeschützte Variablen, die in Zuweisungen verwendet werden, wenn der zugewiesene Wert nicht weiter interessiert. Sie eignen sich besonders zum Dekonstruieren von Tupeln und benutzerdefinierten Typen sowie beim Aufrufen von Methoden mit `out`-Parametern.
- [Mustervergleich](#pattern-matching)
  - Sie können Verzweigungslogik basierend auf beliebigen Typen und Werten der Member dieser Typen erstellen.
- [Lokale `ref`-Variablen und Rückgabetypen](#ref-locals-and-returns)
  - Lokale Variablen und Rückgabewerte von Methoden können Verweise auf andere Speicher sein.
- [Lokale Funktionen](#local-functions)
  - Sie können Funktionen innerhalb von anderen Funktionen verschachteln, um deren Bereich und Sichtbarkeit zu beschränken.
- [Mehr Ausdruckskörpermember](#more-expression-bodied-members)
  - Die Liste der Member, die mithilfe von Ausdrücken erstellt werden können, ist länger geworden.
- [`throw`-Ausdrücke](#throw-expressions)
  - Sie können Ausnahmen in Codekonstrukten auslösen, die vorher nicht zulässig waren, da `throw` eine Anweisung war.
- [Generalisierte asynchrone Rückgabetypen](#generalized-async-return-types)
  - Methoden, die mit dem `async`-Modifizierer deklariert werden, können zusätzlich zu `Task` und `Task<T>` andere Typen zurückgeben.
- [Verbesserung der numerischen literalen Syntax](#numeric-literal-syntax-improvements)
  - Neue Token verbessern die Lesbarkeit für numerische Konstanten.

Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen. Sie werden die Hintergründe jeder einzelnen Funktion erfahren. Sie werden die Syntax erlernen. Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:

1. Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.
1. Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.
1. Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.
1. Führen Sie aus `dotnet try`.

## <a name="out-variables"></a>`out`-Variablen

Die vorhandene Syntax zur Unterstützung von `out`-Parametern wurde in dieser Version verbessert. Nun können Sie `out`-Variablen in der Argumentliste eines Methodenaufrufs deklarieren, anstatt eine separate Deklarationsanweisung zu schreiben:

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

Möglicherweise möchten Sie den Typ der `out`-Variablen aus Gründen der Übersichtlichkeit angeben, wie oben gezeigt. Die Sprache unterstützt jedoch die Verwendung einer implizit typisierten lokalen Variable:

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- Der Code ist einfacher zu lesen.
  - Sie deklarieren die out-Variable, wenn Sie sie verwenden, nicht in einer anderen Zeile weiter oben.
- Sie müssen keinen Anfangswert zuweisen.
  - Durch das Deklarieren der `out`-Variable, wenn sie in einem Methodenaufruf verwendet wird, können Sie diese nicht versehentlich verwenden, bevor sie zugewiesen wurde.

## <a name="tuples"></a>Tupel

C# bietet eine umfangreiche Syntax für Klassen und Strukturen, die verwendet wird, um Ihre Entwurfsabsicht zu erläutern. Aber manchmal erfordert diese umfangreiche Syntax zusätzliche Arbeit mit minimalem Nutzen. Möglicherweise schreiben Sie häufig Methoden, die eine einfache Struktur erfordern, die mehr als ein Datenelement enthält. Zur Unterstützung dieser Szenarios wurden C# *Tupel* hinzugefügt. Tupel sind einfache Datenstrukturen, die mehrere Felder zur Darstellung der Datenmember enthalten.
Die Felder werden nicht überprüft, und Sie können keine eigenen Methoden definieren.

> [!NOTE]
> Tupel waren schon vor C# 7.0 verfügbar, sie waren jedoch ineffizient und hatten keine Sprachunterstützung.
> Das brachte mit sich, dass auf Tupelelemente nur als `Item1`, `Item2` usw. verwiesen werden konnte. Mit C# 7.0 wird Sprachunterstützung für Tupel eingeführt, wodurch semantische Namen für die Felder eines Tupels mit Einsatz neuer, effizienterer Tupeltypen möglich werden.

Sie können ein Tupel erstellen, indem Sie jedem Member einen Wert zuweisen und ihnen optional auch semantische Namen bereitstellen:

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

Das `namedLetters`-Tupel enthält Felder, die als `Alpha` und `Beta` bezeichnet werden. Diese Namen bestehen nur zur Kompilierzeit und werden nicht beibehalten, wenn das Tupel beispielsweise zur Laufzeit mithilfe von Reflektion untersucht wird.

In einer Tupelzuweisung können Sie auch die Namen der Felder auf der rechten Seite der Zuweisung angeben:

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

Manchmal möchten Sie vielleicht die Member eines Tupels entpacken, die von einer Methode zurückgegeben wurden.  Sie können dazu für jeden Wert im Tupel separate Variablen deklarieren. Das Auspacken wird als *Dekonstruieren* des Tupels bezeichnet:

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

Sie können auch eine ähnliche Dekonstruktion für alle Typen in .NET bereitstellen. Schreiben Sie eine `Deconstruct`-Methode als Member der Klasse. Diese `Deconstruct`-Methode bietet eine Reihe von `out`-Argumenten für jede der Eigenschaften, die Sie extrahieren möchten. Berücksichtigen Sie diese `Point`-Klasse, die eine Dekonstruktionsmethode bereitstellt, die die `X`- und `Y`-Koordinaten extrahiert:

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

Sie können die einzelnen Felder extrahieren, indem Sie einem `Point` ein Tupel zuweisen:

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

Ausführliche Informationen zu Tupeln finden Sie im Artikel zu [Tupeln](../tuples.md).

## <a name="discards"></a>Ausschuss

Beim Dekonstruieren eines Tupels oder dem Aufrufen einer Methode mit `out`-Parametern sind Sie gezwungen, eine Variable zu definieren, deren Wert Sie nicht interessiert und die Sie nicht zu verwenden beabsichtigen. C# verfügt jetzt über Unterstützung für *Ausschussvariablen* (discards), um diesem Szenario Rechnung zu tragen. Eine Ausschussvariable ist eine lesegeschützte Variable mit dem Namen `_` (dem Unterstrichzeichen); Sie können der einzelnen Variablen alle Werte zuweisen, die Sie verwerfen möchten. Eine Ausschussvariable ist wie eine nicht zugewiesene Variable; abgesehen von der Zuweisungsanweisung kann die Ausschussvariable nicht in Code verwendet werden.

Ausschussvariablen werden in den folgenden Szenarien unterstützt:

- Beim Dekonstruieren von Tupeln oder benutzerdefinierten Typen.
- Beim Aufrufen von Methoden mit [out](../language-reference/keywords/out-parameter-modifier.md)-Parametern.
- In einem Musterabgleichsvorgang mit den Anweisungen [is](../language-reference/keywords/is.md) und [switch](../language-reference/keywords/switch.md).
- Als eigenständiger Bezeichner, wenn Sie den Wert einer Zuweisung explizit als Ausschuss kennzeichnen möchten.

Das folgende Beispiel definiert eine `QueryCityDataForYears`-Methode, die ein 6-Tupel zurückgibt, das ein Datum für eine Stadt für zwei verschiedene Jahre enthält. Der Methodenaufruf im Beispiel befasst sich nur mit den zwei Bevölkerungswerten, die von der Methode zurückgegeben werden und behandelt so die verbleibenden Werte im Tupel beim Dekonstruieren des Tupels als Ausschuss.

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Weitere Informationen finden Sie unter [Ausschuss](../discards.md).

## <a name="pattern-matching"></a>Musterabgleich

*Mustervergleich* ist ein Funktion, mit der Sie Methodenverteilung für andere Eigenschaften als den Typ eines Objekts implementieren können. Sie sind wahrscheinlich bereits vertraut mit Methodenverteilung, die auf dem Typ eines Objekts basiert. In der objektorientierten Programmierung stellen virtuelle und überschreibende Methoden Sprachsyntax bereit, um die Abfertigung der Methoden basierend auf dem Typ eines Objekts zu implementieren. Basis- und abgeleitete Klassen stellen verschiedene Implementierungen bereit.
Mustervergleichsausdrücke erweitern dieses Konzept, sodass Sie ähnliche Verteilungsmuster für Typen und Datenelemente, die nicht durch eine Vererbungshierarchie verknüpft sind, einfach implementieren können.

Mustervergleich unterstützt `is`-Ausdrücke und `switch`-Ausdrücke. Jeder davon ermöglicht das Überprüfen eines Objekts und dessen Eigenschaften, um zu bestimmen, ob das Objekt dem gesuchten Muster entspricht. Sie verwenden das `when`-Schlüsselwort, um zusätzliche Regeln für das Muster anzugeben.

Der Musterausdruck `is` erweitert den vertrauten [`is`-Operator](../language-reference/keywords/is.md#pattern-matching-with-is), um eine Abfrage zum Typ eines Objekts auszuführen und das Ergebnis in einer Anweisung zuzuweisen. Der folgende Code überprüft, ob es sich bei einer Variablen um einen `int`-Wert handelt und fügt sie, wenn dies der Fall ist, der aktuellen Summe hinzu:

```csharp
if (input is int count)
    sum += count;
```

Das vorausgegangene kleine Beispiel verdeutlicht die Verbesserungen des `is`-Ausdrucks. Sie können für Wert- und Verweistypen testen und das erfolgreiche Ergebnis einer neuen Variable des richtigen Typs zuweisen.

Der Switch-Vergleichsausdruck verfügt über eine vertraute Syntax basierend auf der `switch`-Anweisung, die bereits Teil der C#-Sprache ist. Die aktualisierte Switch-Anweisung verfügt über mehrere neue Konstrukte:

- Der maßgebliche Typ eines `switch`-Ausdrucks ist nicht mehr beschränkt auf ganzzahlige Typen, `Enum`-Typen, `string` oder einen Nullable-Typ, der einem dieser Typen entspricht. Es kann jeder Typ verwendet werden.
- Sie können den Typ des `switch`-Ausdrucks in jeder `case`-Bezeichnung testen. Sie können diesem Typ wie schon beim `is`-Ausdruck eine neue Variable zuweisen.
- Wenn Sie die Bedingungen für diese Variable weiter testen möchten, können Sie eine `when`-Klausel hinzufügen.
- Die Reihenfolge der `case`-Bezeichnungen ist hierbei entscheidend. Die erste Verzweigung, für die eine Übereinstimmung gefunden wird, wird ausgeführt. Alle weiteren werden übersprungen.

Im folgenden Code werden diese Funktionen veranschaulicht:

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- `case 0:` ist das vertraute Konstantenmuster.
- `case IEnumerable<int> childSequence:` ist ein Typmuster.
- `case int n when n > 0:` ist ein Typmuster mit einer zusätzlichen `when`-Bedingung.
- `case null:` ist das NULL-Muster.
- `default:` ist die vertraute Standardanfrage.

Weitere Informationen zum Mustervergleich finden Sie unter [Pattern Matching in C# (Mustervergleich in C#)](../pattern-matching.md).

## <a name="ref-locals-and-returns"></a>Lokale ref-Variablen und Rückgabetypen

Diese Funktion ermöglicht Algorithmen, die Verweise auf Variablen verwenden und zurückgeben, die an anderer Stelle definiert sind. Ein Beispiel ist das Arbeiten mit großen Matrizen und die Suche nach einem einzigen Ort mit bestimmten Eigenschaften. Die folgende Methode gibt einen **Verweis** auf diesen Speicher in der Matrix zurück:

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

Sie können den Rückgabewert als `ref` deklarieren und diesen Wert wie im folgenden Code gezeigt in der Matrix ändern:

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

Die C#-Sprache verfügt über mehrere Regeln, die Sie vor einer falschen Verwendung der lokalen `ref`-Variablen und Rückgabetypen schützen:

- Sie müssen der Methodensignatur und allen `return`-Anweisungen einer Methode das `ref`-Schlüsselwort hinzufügen.
  - Dadurch wird deutlich, dass Rückgaben in der gesamten Methode als Verweis erfolgen.
- Eine `ref return`-Rückgabe kann einer Wert- oder einer `ref`-Variablen zugewiesen werden.
  - Der Aufrufer steuert, ob der Rückgabewert kopiert werden soll. Durch Auslassen des `ref`-Modifizierers beim Zuweisen des Rückgabewerts gibt der Aufrufer an, dass der Wert kopiert werden und nicht etwa ein Verweis auf den Speicher erfolgen soll.
- Sie können einer lokalen `ref`-Variablen keinen Rückgabewert einer Standardmethode zuweisen.
  - Dadurch werden Aussagen wie `ref int i = sequence.Count();` nicht zugelassen.
- Sie können `ref` nicht an eine Variable zurückgeben, deren Lebensdauer nicht über die Ausführung der Methode hinausgeht.
  - Das bedeutet, dass Sie keinen Verweis auf eine lokale Variable oder eine Variable mit einem ähnlichen Bereich zurückgeben können.
- Lokale `ref`-Variablen und Rückgabewerte können nicht in Verbindung mit asynchronen Methoden verwendet werden.
  - Der Compiler kann nicht feststellen, ob die Variable, auf die verwiesen wird, bei der Rückgabe der asynchronen Methode auf ihren endgültigen Wert festgelegt ist.

Das Hinzufügen von lokalen ref-Variablen und ref-Rückgaben ermöglicht effizientere Algorithmen, da Werte nicht kopiert oder dereferenzierende Vorgänge nicht mehrmals ausgeführt werden.

Das Hinzufügen von `ref` zum Rückgabewert stellt eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes) dar. Vorhandener Code lässt sich kompilieren, der ref-Rückgabewert wird aber bei der Zuweisung kopiert. Aufrufer müssen den Speicher für den Rückgabewert in eine lokale `ref`-Variable aktualisieren, um die Rückgabe als Verweis zu speichern.

Weitere Informationen finden Sie im Artikel [Schlüsselwort „ref“](../language-reference/keywords/ref.md).

## <a name="local-functions"></a>Lokale Funktionen

Viele Entwürfe für Klassen enthalten Methoden, die nur von einer Stelle aufgerufen werden. Durch diese zusätzlichen privaten Methoden bleibt jede Methode klein und konzentriert. Mit *lokalen Funktionen* können Sie Methoden innerhalb des Kontexts einer anderen Methode deklarieren. So können Leser der Klasse leichter erkennen, dass die lokale Methode nur aus dem Kontext aufgerufen wird, in dem sie deklariert wird.

Es gibt zwei häufige Anwendungsfälle für lokale Funktionen: öffentliche Iteratormethoden und öffentliche asynchrone Methoden. Beide Arten von Methoden generieren Code, der Fehler später meldet, als Programmierer erwarten würden. Bei Iteratormethoden werden Ausnahmen nur festgestellt, wenn Code aufgerufen wird, der die zurückgegebene Sequenz auflistet. Bei asynchronen Methoden werden Ausnahmen nur festgestellt, wenn der zurückgegebene `Task`-Wert erwartet wird. Im folgenden Beispiel wird veranschaulicht, wie mithilfe einer lokalen Funktion die Überprüfung der Parameter von der Iteratorimplementierung getrennt wird:

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

Das gleiche Verfahren kann mit `async`-Methoden eingesetzt werden, um sicherzustellen, dass Ausnahmen aufgrund der Argumentüberprüfung ausgelöst werden, bevor die asynchrone Arbeit beginnt:

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

> [!NOTE]
> Einige der Entwürfe, die von lokalen Funktionen unterstützt werden, können auch mithilfe von *Lambdaausdrücken* erreicht werden. Weitere Informationen finden Sie unter [Lokale Funktionen im Vergleich zu Lambdaausdrücken](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).

## <a name="more-expression-bodied-members"></a>Mehr Ausdruckskörpermember

In C# 6 wurden [Ausdruckskörpermember](csharp-6.md#expression-bodied-function-members) für Memberfunktionen und schreibgeschützte Eigenschaften eingeführt. Mit C# 7.0 werden die zulässigen Member erweitert, die als Ausdrücke implementiert werden können. In C# 7.0 können Sie *Konstruktoren*, *Finalizer* sowie `get`- und `set`-Zugriffsmethoden für *Eigenschaften* und *Indexer* implementieren. Der folgende Code zeigt entsprechende Beispiele:

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> In diesem Beispiel ist kein Finalizer erforderlich, aber damit soll die Syntax dargestellt werden. Sie sollten in Ihrer Klasse nur einen Finalizer implementieren, wenn es notwendig ist, nicht verwaltete Ressourcen freizugeben. Sie sollten auch die Verwendung der <xref:System.Runtime.InteropServices.SafeHandle>-Klasse in Betracht ziehen, anstatt nicht verwaltete Ressourcen direkt zu verwalten.

Diese neuen Speicherorte für Member mit Ausdruckskörper sind ein wichtiger Meilenstein für die Sprache C#: Diese Features wurden von Community-Mitgliedern implementiert, die am Open Source-Projekt [Roslyn](https://github.com/dotnet/Roslyn) arbeiten.

Das Ändern einer Methode in ein Ausdruckskörpermember ist eine [binärkompatible](version-update-considerations.md#binary-compatible-changes) Änderung.

## <a name="throw-expressions"></a>Throw-Ausdrücke

In C# ist `throw` schon immer eine Anweisung. Da `throw` eine Anweisung und kein Ausdruck ist, gab es C#-Konstrukte, in denen diese Anweisung nicht verwendet werden konnte. Darunter waren bedingte Ausdrücke, NULL-Sammelausdrücke und einige Lambdaausdrücke. Das Hinzufügen von Ausdruckskörpermembern fügt mehr Speicherorte hinzu, bei denen `throw`-Ausdrücke nützlich wären. Damit Sie diese Konstrukte schreiben können, wurden in C# 7.0 [*Throw-Ausdrücke*](../language-reference/keywords/throw.md#the-throw-expression) eingeführt.

Diese Ergänzung erleichtert das Schreiben ausdrucksbasierteren Codes. Sie benötigen zur Fehlerüberprüfung keine weiteren Anweisungen.

## <a name="generalized-async-return-types"></a>Generalisierte asynchrone Rückgabetypen

Das Zurückgeben eines `Task`-Objekts von asynchronen Methoden kann Leistungsengpässe in bestimmten Pfaden verursachen. `Task` ist ein Verweistyp, seine Verwendung bedeutet also das Zuordnen eines Objekts. In Fällen, in denen eine mit dem `async`-Modifizierer deklarierte Methode ein zwischengespeichertes Ergebnis zurückgibt oder synchron abschließt, können die zusätzlichen Zuordnungen viel Zeit bei der Ausführung kritischer Codeabschnitte kosten. Es kann kostspielig werden, wenn diese Zuordnungen in engen Schleifen auftreten.

Durch die neue Sprachfunktion sind die Rückgabetypen asynchroner Methoden nicht auf `Task`, `Task<T>` und `void` beschränkt. Der zurückgegebene Typ muss noch immer das asynchrone Muster erfüllen, d.h. dass eine `GetAwaiter`-Methode verfügbar sein muss. Als konkretes Beispiel wurde der `ValueTask`-Typ zu .NET hinzugefügt, um diese neue Sprachfunktion zu nutzen:

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> Sie müssen das NuGet-Paket hinzufügen [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/), um den Typ <xref:System.Threading.Tasks.ValueTask%601> verwenden zu können.

Diese Verbesserung ist besonders für Bibliotheksautoren hilfreich, um die Zuordnung von `Task` in leistungskritischem Code zu verhindern.

## <a name="numeric-literal-syntax-improvements"></a>Verbesserung der numerischen literalen Syntax

Falsches Lesen numerischer Konstanten kann Code beim ersten Lesen schwerer verständlich machen. Bitmasken oder andere symbolische Werte können Missverständnisse hervorrufen. C# 7.0 enthält zwei neue Funktionen, mit denen Zahlen für den beabsichtigten Zweck so lesbar wie möglich geschrieben werden können: *binäre Literale* und *Zifferntrennzeichen*.

Beim Erstellen von Bitmasken oder wenn die binäre Darstellung einer Zahl den Code besonders gut lesbar macht, sollten Sie diese Zahl im Binärformat schreiben:

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

Das `0b` am Anfang der Konstante gibt an, dass die Zahl als binäre Zahl geschrieben wird. Binäre Zahlen können lang werden. Daher kann die Einführung des `_` als Zifferntrennzeichen wie in der binären Konstante oben gezeigt die Bitmuster übersichtlicher machen. Das Zifferntrennzeichen kann überall in der Konstante angezeigt werden. Für Zahlen der Basis 10 wird es üblicherweise als Tausendertrennzeichen verwendet:

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

Das Zifferntrennzeichen kann auch mit `decimal`-, `float`- und `double`-Typen verwendet werden:

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

Insgesamt können Sie numerische Konstanten viel leserlicher deklarieren.
