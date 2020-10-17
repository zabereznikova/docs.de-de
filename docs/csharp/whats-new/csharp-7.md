---
title: Neues in C# 7.0 – C#-Leitfaden
description: Erhalten Sie einen Überblick über die neuen Funktionen in Version 7.0 der C#-Sprache.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 84f5961d573b99438320a75d7f89bc7fd94f6266
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955212"
---
# <a name="whats-new-in-c-70-through-c-73"></a>Neuerungen von C# 7.0 bis C# 7.3

Von C# 7.0 bis C# 7.3 wurden zahlreiche Features für und inkrementelle Verbesserungen an den Entwicklungsfunktionen von C# eingeführt. In diesem Artikel erhalten Sie einen Überblick über die neuen Sprachfeatures und Compileroptionen. In den Beschreibungen wird das Verhalten für C# 7.3 erläutert. Dabei handelt es sich um die aktuelle Version, die für auf dem .NET Framework basierende Anwendungen unterstützt wird.

Das Konfigurationselement für die [Sprachversionsauswahl](../language-reference/configure-language-version.md) wurde im Rahmen von C# 7.1 hinzugefügt. Damit können Sie die Compilersprachenversion in Ihrer Projektdatei angeben.

Von C# 7.0 bis C# 7.3 wurden der C#-Sprache die folgenden Features und Designs hinzugefügt:

- [Tupel und Verwerfen](#tuples-and-discards)
  - Sie können einfache, unbenannte Typen erstellen, die mehrere öffentliche Felder enthalten. Compiler und IDE-Tools kennen die Semantik dieser Typen.
  - Ausschussvariablen (discards) sind temporäre, lesegeschützte Variablen, die in Zuweisungen verwendet werden, wenn der zugewiesene Wert nicht weiter interessiert. Sie eignen sich besonders zum Dekonstruieren von Tupeln und benutzerdefinierten Typen sowie beim Aufrufen von Methoden mit `out`-Parametern.
- [Mustervergleich](#pattern-matching)
  - Sie können Verzweigungslogik basierend auf beliebigen Typen und Werten der Member dieser Typen erstellen.
- [`async` `Main`-Methode](#async-main)
  - Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.
- [Lokale Funktionen](#local-functions)
  - Sie können Funktionen innerhalb von anderen Funktionen verschachteln, um deren Bereich und Sichtbarkeit zu beschränken.
- [Mehr Ausdruckskörpermember](#more-expression-bodied-members)
  - Die Liste der Member, die mithilfe von Ausdrücken erstellt werden können, ist länger geworden.
- [`throw`-Ausdrücke](#throw-expressions)
  - Sie können Ausnahmen in Codekonstrukten auslösen, die vorher nicht zulässig waren, da `throw` eine Anweisung war.
- [`default`Literale Ausdrücke](#default-literal-expressions)
  - Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.
- [Verbesserung der numerischen literalen Syntax](#numeric-literal-syntax-improvements)
  - Neue Token verbessern die Lesbarkeit für numerische Konstanten.
- [`out`Variablen](#out-variables)
  - Sie können `out`-Werte als Inlineargumente für die Methode deklarieren, wenn sie verwendet werden.
- [Nicht schließende benannte Argumente](#non-trailing-named-arguments)
  - Positionelle Argumente können auf benannte Argumente folgen.
- [`private protected`-Zugriffsmodifizierer](#private-protected-access-modifier)
  - Der `private protected`-Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen innerhalb der gleichen Assembly.
- [Verbesserte Überladungsauflösung](#improved-overload-candidates)
  - Neue Regeln sorgen nun für die Auflösung von Ambiguitäten bei Überladungsauflösungen.
- [Techniken zum Schreiben von sicherem, effizientem Code](#enabling-more-efficient-safe-code)
  - Eine Kombination aus Verbesserungen der Syntax, die das Arbeiten mit Werttypen mithilfe von Verweissemantik ermöglichen.

Schließlich verfügt der Compiler über neue Optionen:

- `-refout` und `-refonly`, wodurch die [Erstellung von Referenzassemblys](#reference-assembly-generation) gesteuert wird.
- `-publicsign`, um das Signieren von Assemblys durch Open Source Software (OSS) zu ermöglichen.
- `-pathmap`, um eine Zuordnung für Quellverzeichnisse bereitzustellen.

Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen. Sie werden die Hintergründe sowie die Syntax jedes einzelnen Features kennenlernen. Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:

1. Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.
1. Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.
1. Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.
1. Führen Sie aus `dotnet try`.

## <a name="tuples-and-discards"></a>Tupel und Verwerfen

C# bietet eine umfangreiche Syntax für Klassen und Strukturen, die verwendet wird, um Ihre Entwurfsabsicht zu erläutern. Aber manchmal erfordert diese umfangreiche Syntax zusätzliche Arbeit mit minimalem Nutzen. Möglicherweise schreiben Sie häufig Methoden, die eine einfache Struktur erfordern, die mehr als ein Datenelement enthält. Zur Unterstützung dieser Szenarios wurden C# *Tupel* hinzugefügt. Tupel sind einfache Datenstrukturen, die mehrere Felder zur Darstellung der Datenmember enthalten. Die Felder werden nicht überprüft, und Sie können keine eigenen Methoden definieren. C#-Tupeltypen unterstützen `==` und `!=`. Weitere Informationen.

> [!NOTE]
> Tupel waren schon vor C# 7.0 verfügbar, sie waren jedoch ineffizient und hatten keine Sprachunterstützung. Das brachte mit sich, dass auf Tupelelemente nur als `Item1`, `Item2` usw. verwiesen werden konnte. Mit C# 7.0 wird Sprachunterstützung für Tupel eingeführt, wodurch semantische Namen für die Felder eines Tupels mit Einsatz neuer, effizienterer Tupeltypen möglich werden.

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

Wenn Sie einen Tupel initialisieren, sind die Variablen, die für die rechte Seite der Zuweisung verwendet werden, oft dieselben, wie die Namen, die Sie den Tupelelementen geben möchten. Die Namen von Tupelelementen können von den Variablen abgeleitet werden, die zum Initialisieren der Tupel verwendet werden:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Weitere Informationen zu diesem Feature finden Sie im Artikel [Tupeltypen](../language-reference/builtin-types/value-tuples.md).

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

Beim *Musterabgleich* handelt es sich um mehrere Features, die neue Möglichkeiten eröffnen, Ablaufsteuerung in Ihrem Code auszudrücken. Sie können Variablen nach Typ, Werten oder den Werten ihrer Eigenschaften testen. Dieses Vorgehen sorgt für einen besser lesbaren Codeflow.

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

Ab C# 7.1 kann der Musterausdruck für `is` und das `switch`-Typmuster den Typ eines generischen Typparameters haben. Dies kann sehr nützlich sein, wenn Sie Typen überprüfen, die entweder `struct`- oder `class`-Typen sein können, und Sie Boxing vermeiden möchten.

Weitere Informationen zum Mustervergleich finden Sie unter [Pattern Matching in C# (Mustervergleich in C#)](../pattern-matching.md).

## <a name="async-main"></a>Async Main

Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden. Vorher hätten Sie das Folgende schreiben müssen:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Nun können Sie das Folgende schreiben:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Wenn Ihr Programm keinen Exitcode zurückgibt, können Sie eine `Main`-Methode deklarieren, die einen <xref:System.Threading.Tasks.Task> zurückgibt:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

Ausführliche Informationen finden Sie unter [Async Main](../programming-guide/main-and-command-args/index.md) im Programmierhandbuch.

## <a name="local-functions"></a>Lokale Funktionen

Viele Entwürfe für Klassen enthalten Methoden, die nur von einer Stelle aufgerufen werden. Durch diese zusätzlichen privaten Methoden bleibt jede Methode klein und konzentriert. Mit *lokalen Funktionen* können Sie Methoden innerhalb des Kontexts einer anderen Methode deklarieren. So können Leser der Klasse leichter erkennen, dass die lokale Methode nur aus dem Kontext aufgerufen wird, in dem sie deklariert wird.

Es gibt zwei häufige Anwendungsfälle für lokale Funktionen: öffentliche Iteratormethoden und öffentliche asynchrone Methoden. Beide Arten von Methoden generieren Code, der Fehler später meldet, als Programmierer erwarten würden. Bei Iteratormethoden werden Ausnahmen nur festgestellt, wenn Code aufgerufen wird, der die zurückgegebene Sequenz auflistet. Bei asynchronen Methoden werden Ausnahmen nur festgestellt, wenn der zurückgegebene `Task`-Wert erwartet wird. Im folgenden Beispiel wird veranschaulicht, wie mithilfe einer lokalen Funktion die Überprüfung der Parameter von der Iteratorimplementierung getrennt wird:

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

Das gleiche Verfahren kann mit `async`-Methoden eingesetzt werden, um sicherzustellen, dass Ausnahmen aufgrund der Argumentüberprüfung ausgelöst werden, bevor die asynchrone Arbeit beginnt:

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Diese Syntax wird jetzt unterstützt:

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

Das Attribut `SomeThingAboutFieldAttribute` wird auf das vom Compiler generierte Unterstützungsfeld für `SomeProperty` angewendet. Weitere Informationen finden Sie unter [attributes](../programming-guide/concepts/attributes/index.md) im C#-Programmierhandbuch.

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

## <a name="default-literal-expressions"></a>Literale Standardausdrücke

Literale Standardausdrücke sind eine Erweiterung von Ausdrücken mit Standardwert. Diese Ausdrücke initialisieren eine Variable auf dem Standardwert. Dort, wo Sie vorher das Folgende geschrieben haben:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Können Sie nun den Typ weglassen, der auf der rechten Seite der Initialisierung steht.

```csharp
Func<string, bool> whereClause = default;
```

Weitere Informationen finden Sie im Abschnitt [Standardliteral](../language-reference/operators/default.md#default-literal) des Artikels zum [default-Operator](../language-reference/operators/default.md).

## <a name="numeric-literal-syntax-improvements"></a>Verbesserung der numerischen literalen Syntax

Falsches Lesen numerischer Konstanten kann Code beim ersten Lesen schwerer verständlich machen. Bitmasken oder andere symbolische Werte können Missverständnisse hervorrufen. C# 7.0 enthält zwei neue Funktionen, mit denen Zahlen für den beabsichtigten Zweck so lesbar wie möglich geschrieben werden können: *binäre Literale* und *Zifferntrennzeichen*.

Beim Erstellen von Bitmasken oder wenn die binäre Darstellung einer Zahl den Code besonders gut lesbar macht, sollten Sie diese Zahl im Binärformat schreiben:

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

Das `0b` am Anfang der Konstante gibt an, dass die Zahl als binäre Zahl geschrieben wird. Binäre Zahlen können lang werden. Daher kann die Einführung von `_` als Ziffertrennzeichen wie in der binären Konstante im vorherigen Beispiel gezeigt die Bitmuster übersichtlicher machen. Das Zifferntrennzeichen kann überall in der Konstante angezeigt werden. Für Zahlen der Basis 10 wird es üblicherweise als Tausendertrennzeichen verwendet. Hexadezimale und binäre numerische Literale dürfen jetzt mit `_` beginnen:

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

Das Zifferntrennzeichen kann auch mit `decimal`-, `float`- und `double`-Typen verwendet werden:

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

Insgesamt können Sie numerische Konstanten viel leserlicher deklarieren.

## <a name="out-variables"></a>`out`-Variablen

Die vorhandene Syntax zur Unterstützung von `out`-Parametern wurde in C# 7 verbessert. Nun können Sie `out`-Variablen in der Argumentliste eines Methodenaufrufs deklarieren, anstatt eine separate Deklarationsanweisung zu schreiben:

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

Sie sollten den Typ der `out`-Variablen aus Gründen der Übersichtlichkeit angeben. Dies wird im vorherigen Beispiel veranschaulicht. Die Sprache unterstützt jedoch die Verwendung einer implizit typisierten lokalen Variable:

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- Der Code ist einfacher zu lesen.
  - Sie deklarieren die out-Variable, wenn Sie sie verwenden, nicht in einer anderen Codezeile weiter oben.
- Sie müssen keinen Anfangswert zuweisen.
  - Durch das Deklarieren der `out`-Variable, wenn sie in einem Methodenaufruf verwendet wird, können Sie diese nicht versehentlich verwenden, bevor sie zugewiesen wurde.

Die in C# 7.0 zum Zulassen von `out`-Variablendeklarationen hinzugefügte Syntax wurde erweitert, sodass sie Feldinitialisierer, Eigenschafteninitialisierer, Konstruktorinitialisierer und Abfrageklauseln umfasst. Sie ermöglicht Code wie im folgenden Beispiel:

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a>Nicht schließende benannte Argumente

Methodenaufrufe dürfen jetzt benannte Argumente verwenden, die positionellen Argumenten vorstehen, wenn diese benannten Argumente in der richtigen Position verwendet werden. Weitere Informationen finden Sie unter [Benannte und optionale Argumente (C#-Programmierhandbuch)](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="private-protected-access-modifier"></a>Zugriffsmodifizierer *private protected*

Ein neuer zusammengesetzter Zugriffsmodifizierer: `private protected` zeigt an, dass auf ein Element durch eine es enthaltende Klasse oder durch innerhalb der gleichen Assembly deklarierte abgeleitete Klassen zugegriffen werden darf. Während `protected internal` den Zugriff durch abgeleitete Klassen oder Klassen, die sich in der gleichen Assembly befinden, erlaubt, schränkt `private protected` den Zugriff auf innerhalb der gleichen Assembly deklarierte abgeleitete Typen ein.

Weitere Informationen finden Sie unter [Zugriffsmodifizierer (C#-Referenz)](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.

## <a name="improved-overload-candidates"></a>Verbesserte Überladungskandidaten

In jedem Release werden die Überladungsauflösungsregeln für Situationen aktualisiert, in denen mehrdeutige Methodenaufrufe eine „naheliegende“ Auswahlmöglichkeit haben. In diesem Release werden drei neue Regeln hinzufügt, damit der Compiler die naheliegende Auswahlmöglichkeit nutzt:

1. Wenn eine Methodengruppe sowohl Instanz- als auch statische Member enthält, verwirft der Compiler die Instanzmember, wenn die Methode ohne Instanzempfänger oder -kontext aufgerufen wurde. Der Compiler verwirft die statischen Member, wenn die Methode mit einem Instanzempfänger aufgerufen wurde. Wenn kein Empfänger vorhanden ist, bezieht der Compiler nur statische Member in einen statischen Kontext ein – andernfalls sowohl statische als auch Instanzmember. Wenn unklar ist, ob der Empfänger eine Instanz oder ein Typ ist, bezieht der Compiler beides ein. Ein statischer Kontext, wo ein impliziter `this`-Instanzempfänger nicht verwendet werden kann, enthält den Text von Membern, wo kein `this` definiert ist, z.B. statische Member, sowie Orte, an denen `this` nicht verwendet werden kann, z.B. Feld- und Konstruktorinitialisierer.
1. Wenn eine Methodengruppe einige generische Methoden enthält, deren Typargumente ihre Einschränkungen nicht erfüllen, werden diese Member aus dem Satz von Kandidaten entfernt.
1. Für eine Methodengruppenkonvertierung werden Kandidatenmethoden, deren Rückgabetyp nicht mit dem des Delegaten übereinstimmt, aus dem Satz entfernt.

Sie werden diese Änderung bemerken, da Sie weniger Compilerfehler für mehrdeutige Methodenüberladungen finden werden, wenn Sie sicher sind, welche Methode besser ist.

## <a name="enabling-more-efficient-safe-code"></a>Ermöglichen von effizienterem sicherem Code

Sie sollten C#-Code sicher schreiben können, der so leistungsstark ist wie unsicherer Code. Sicherer Code vermeidet Fehlerklassen, z.B. Pufferüberläufe, verirrte Zeiger und andere Fehler beim Arbeitsspeicherzugriff. Diese neuen Features erweitern die Funktionen des überprüfbaren sicheren Codes. Schreiben Sie mithilfe sicherer Konstrukte mehr Code. Diese Features erleichtern dies.

Die folgenden neuen Features unterstützen das Design der besseren Leistung für sicheren Code:

- Sie können ohne Anheften auf feste Felder zugreifen.
- Sie können `ref` erneut lokale Variablen zuweisen.
- Sie können Initialisierer auf `stackalloc`-Arrays verwenden.
- Sie können `fixed`-Anweisungen mit jedem Typ verwenden, der ein Muster unterstützt.
- Sie können zusätzliche generische Einschränkungen verwenden.
- Den `in`-Modifizierer für Parameter zur Angabe, dass ein Argument durch Verweis übergeben, von der aufgerufenen Methode aber nicht verändert wird. Das Hinzufügen des Modifizierers `in` zu einem Argument ist eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes).
- Der `ref readonly`-Modifizierer für die Methodenrückgabe, um anzugeben, dass eine Methode ihren Wert als Verweis zurückgibt und keinen Schreibzugriff auf dieses Objekt zulässt. Das Hinzufügen des Modifizierers `ref readonly` ist eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes), wenn die Rückgabe einem Wert zugewiesen wird. Das Hinzufügen des Modifizierers `readonly` zu einer vorhandenen `ref`-Rückgabeanweisung ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes). Es verlangt von Aufrufern das Aktualisieren der lokalen `ref`-Variablen, um den `readonly`-Modifizierer einzuschließen.
- Die `readonly struct`-Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und ihren Membermethoden als `in`-Parameter übergeben werden sollte. Das Hinzufügen des Modifizierers `readonly` zu einer vorhandenen Strukturdeklaration ist eine [binärkompatible Änderung](version-update-considerations.md#binary-compatible-changes).
- Die `ref struct`-Deklaration, um anzugeben, dass ein Strukturtyp direkt auf verwalteten Arbeitsspeicher zugreift und immer per Stapel zugeordnet werden muss. Das Hinzufügen des Modifizierers `ref` zu einer vorhandenen `struct`-Deklaration ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes). Ein `ref struct` kann kein Mitglied einer Klasse sein oder an anderen Stellen verwendet werden, wo es auf dem Heap zugewiesen werden könnte.

Weitere Informationen zu all diesen Änderungen finden Sie unter [Schreiben von sicherem und effizientem Code](../write-safe-efficient-code.md).

### <a name="ref-locals-and-returns"></a>Lokale ref-Variablen und Rückgabetypen

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

Lokale `ref`-Variablen werden jetzt möglicherweise neu zugewiesen, um nach der Initialisierung auf verschiedene Instanzen zu verweisen. Der folgende Code wird jetzt kompiliert:

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

Weitere Informationen finden Sie im Artikel zu [`ref`-Rückgaben und lokalen `ref`-Variablen](../programming-guide/classes-and-structs/ref-returns.md) und im Artikel zu [`foreach`](../language-reference/keywords/foreach-in.md).

Weitere Informationen finden Sie im Artikel [Schlüsselwort „ref“](../language-reference/keywords/ref.md).

### <a name="conditional-ref-expressions"></a>Bedingte `ref` Ausdrücke

Schließlich kann ein bedingter Ausdruck als Ergebnis einen Verweis anstatt eines Werts erzeugen. Beispielsweise würden Sie folgendes schreiben, um einen Verweis auf das erste Element in einem von zwei Arrays abzurufen:

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

Die Variable `r` ist ein Verweis auf den ersten Wert in `arr` oder `otherArr`.

Weitere Informationen finden Sie unter [conditional-Operator (?:)](../language-reference/operators/conditional-operator.md) in der Sprachreferenz.

### <a name="in-parameter-modifier"></a>Modifizierer für `in`-Parameter

Das `in`-Schlüsselwort ergänzt die vorhandenen Schlüsselwörter ref und out zum Übergeben von Argumenten als Verweis. Durch das `in`-Schlüsselwort wird festgelegt, dass das Argument als Verweis übergeben wird, die aufgerufene Methode aber nicht den Wert ändert.

Sie können Überladungen, die nach Wert oder nach schreibgeschütztem Verweis übergeben werden, wie im folgenden Code gezeigt deklarieren:

```csharp
static void M(S arg);
static void M(in S arg);
```

Die Überladung, die nach Wert übergeben wird (die erste im obigen Beispiel) ist besser als die Version, die nach schreibgeschütztem Verweis übergeben wird. Um die Version mit dem readonly-Verweisargument aufzurufen, müssen Sie auch den `in`-Modifizierer beim Aufrufen der Methode einbeziehen.

Weitere Informationen finden Sie im Artikel zum [`in`-Parametermodifizierer](../language-reference/keywords/in-parameter-modifier.md).

### <a name="more-types-support-the-fixed-statement"></a>Weitere Typen unterstützen die `fixed`-Anweisung

Die `fixed`-Anweisung unterstützte eine begrenzte Anzahl von Typen. Ab C# 7.3 kann jeder Typ, der eine `GetPinnableReference()`-Methode enthält, die eine `ref T` oder `ref readonly T` zurückgibt, `fixed` sein. Dieses Feature hinzuzufügen, bedeutet, dass `fixed` mit <xref:System.Span%601?displayProperty=nameWithType> und verwandten Typen genutzt werden kann.

Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md) in der Sprachreferenz.

### <a name="indexing-fixed-fields-does-not-require-pinning"></a>Indizieren von `fixed`-Feldern erfordert kein Anheften

Betrachten Sie diese Struktur:

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

In früheren Versionen von C# mussten Sie eine Variable für den Zugriff auf eine der ganzen Zahlen anheften, die Teil von `myFixedField` sind. Der folgende Code wird kompiliert, ohne die Variable `p` in einer separaten `fixed`-Anweisung anzuheften:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

Die Variable `p` greift auf ein Element in `myFixedField` zu. Sie müssen keine separate `int*`-Variable deklarieren. Sie benötigen weiterhin einen `unsafe`-Kontext. In früheren Versionen von C# müssen Sie einen zweiten festen Zeiger deklarieren:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md).

### <a name="stackalloc-arrays-support-initializers"></a>`stackalloc`-Arrays unterstützen Initialisierer

Sie konnten schon die Werte für Elemente in einem Array angeben, wenn Sie es initialisierten:

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

Nun kann die gleiche Syntax auf Arrays angewendet werden, die mit `stackalloc` deklariert werden:

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

Weitere Informationen finden Sie im Artikel zum [`stackalloc`-Operator](../language-reference/operators/stackalloc.md).

### <a name="enhanced-generic-constraints"></a>Verbesserte generische Einschränkungen

Sie können jetzt Typ <xref:System.Enum?displayProperty=nameWithType> oder <xref:System.Delegate?displayProperty=nameWithType> als Basisklasseneinschränkungen für einen Typparameter angeben.

Sie können auch die neue `unmanaged`-Einschränkung nutzen, um anzugeben, dass der Typparameter ein [nicht verwalteter Non-Nullable-Typ](../language-reference/builtin-types/unmanaged-types.md) sein muss.

Weitere Informationen finden Sie in den Artikeln zu generischen [`where`-Einschränkungen](../language-reference/keywords/where-generic-type-constraint.md) und [Einschränkungen für Typparameter](../programming-guide/generics/constraints-on-type-parameters.md).

Das Hinzufügen dieser Einschränkungen zu vorhandenen Typen ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes). Geschlossene generische Typen erfüllen diese neuen Einschränkungen möglicherweise nicht mehr.

### <a name="generalized-async-return-types"></a>Generalisierte asynchrone Rückgabetypen

Das Zurückgeben eines `Task`-Objekts von asynchronen Methoden kann Leistungsengpässe in bestimmten Pfaden verursachen. `Task` ist ein Verweistyp, seine Verwendung bedeutet also das Zuordnen eines Objekts. In Fällen, in denen eine mit dem `async`-Modifizierer deklarierte Methode ein zwischengespeichertes Ergebnis zurückgibt oder synchron abschließt, können die zusätzlichen Zuordnungen viel Zeit bei der Ausführung kritischer Codeabschnitte kosten. Es kann kostspielig werden, wenn diese Zuordnungen in engen Schleifen auftreten.

Durch die neue Sprachfunktion sind die Rückgabetypen asynchroner Methoden nicht auf `Task`, `Task<T>` und `void` beschränkt. Der zurückgegebene Typ muss noch immer das asynchrone Muster erfüllen, d.h. dass eine `GetAwaiter`-Methode verfügbar sein muss. Als konkretes Beispiel wurde der `ValueTask`-Typ zu .NET hinzugefügt, um diese neue Sprachfunktion zu nutzen:

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> Sie müssen das NuGet-Paket [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) hinzufügen, um den Typ <xref:System.Threading.Tasks.ValueTask%601> verwenden zu können.

Diese Verbesserung ist besonders für Bibliotheksautoren hilfreich, um die Zuordnung von `Task` in leistungskritischem Code zu verhindern.

## <a name="new-compiler-options"></a>Neue Compileroptionen

Neue Compileroptionen unterstützen neue Build- und DevOpsszenarien für C#-Programme.

### <a name="reference-assembly-generation"></a>Generierung der Referenzassembly

Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [-refout](../language-reference/compiler-options/refout-compiler-option.md) und [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).
In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.

### <a name="public-or-open-source-signing"></a>Öffentliche oder Open Source-Signierung

Die `-publicsign`-Compileroption weist den Compiler an, die Assembly mit einem öffentlichen Schlüssel zu signieren. Die Assembly wird als signiert markiert, aber die Signatur wird dem öffentlichen Schlüssel entnommen. Mit dieser Option können Sie signierte Assemblys aus Open Source-Projekten mit einem öffentlichen Schlüssel erstellen.

Weitere Informationen finden Sie im Artikel zur [Compileroption „-publicsign“](../language-reference/compiler-options/publicsign-compiler-option.md).

### <a name="pathmap"></a>pathmap

Die `-pathmap`-Compileroption weist den Compiler an, Quellpfade aus der Buildumgebung mit zugeordneten Quellpfaden zu ersetzen. Die `-pathmap`-Option bestimmt den Quellpfad, der vom Compiler in PDB-Dateien oder für <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> geschrieben wird.

Weitere Informationen finden Sie im Artikel zur [Compileroption „-pathmap“](../language-reference/compiler-options/pathmap-compiler-option.md).
