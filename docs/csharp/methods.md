---
title: Methoden (Leitfaden für C#)
description: Übersicht über Methoden, Methodenparameter und Methodenrückgabewerte
ms.technology: csharp-fundamentals
ms.date: 05/21/2018
ms.assetid: 577a8527-1081-4b36-9b9e-0685b6553c6e
ms.openlocfilehash: 520aeed85ee00127c2bd3eee681b980d05f46d05
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874707"
---
# <a name="methods-in-c"></a>Methoden in C#

Eine Methode ist ein Codeblock, der eine Reihe von Anweisungen enthält. Ein Programm bewirkt die Ausführung der Anweisungen, indem die Methode aufgerufen wird und alle erforderlichen Methodenargumente angegeben werden. In C# werden alle Anweisungen im Kontext einer Methode ausgeführt. Die Methode `Main` ist der Einstiegspunkt jeder C#-Anwendung und wird von der Common Language Runtime (CLR) aufgerufen, wenn das Programm gestartet wird.

> [!NOTE]
> In diesem Thema werden benannte Methoden erläutert. Informationen über anonyme Funktionen finden Sie unter [Anonyme Funktionen](programming-guide/statements-expressions-operators/anonymous-functions.md).

<a name="signatures"></a>

## <a name="method-signatures"></a>Methodensignaturen

Methoden werden in `class` oder `struct` durch folgende Angaben deklariert:

- Eine optionale Zugriffsebene, z.B. `public` oder `private`. Der Standardwert ist `private`.
- Optionale Modifizierer, z.B. `abstract` oder `sealed`.
- Der Rückgabewert oder `void`, wenn die Methode keinen besitzt.
- Der Methodenname.
- Jede Methodenparameter. Methodenparameter werden in Klammern eingeschlossen und durch Kommas getrennt. Leere Klammern geben an, dass für die Methode keine Parameter erforderlich sind.

Diese Teile bilden zusammen die Signatur der Methode.

> [!IMPORTANT]
> Ein Rückgabetyp einer Methode ist nicht Teil der Signatur der Methode, wenn es um die Methodenüberladung geht. Er ist jedoch Teil der Methodensignatur, wenn die Kompatibilität zwischen einem Delegaten und der Methode bestimmt wird, auf die dieser verweist.

Im folgenden Beispiel wird eine Klasse mit dem Namen `Motorcycle` deklariert, die fünf Methoden enthält:

[!code-csharp[csSnippets.Methods#40](../../samples/snippets/csharp/concepts/methods/methods40.cs#40)]

Beachten Sie, dass die `Motorcycle`-Klasse eine überladene Methode, `Drive`, enthält. Zwei Methoden haben denselben Namen, müssen aber durch ihre Parametertypen unterschieden werden.

<a name="invocation"></a>

## <a name="method-invocation"></a>Methodenaufruf

Methoden können entweder *instance* oder *static* sein. Das Aufrufen einer Instanzmethode erfordert, dass Sie ein Objekt instanziieren und die Methode an diesem Objekt aufrufen; eine Instanzmethode funktioniert in dieser Instanz und ihren Daten. Sie rufen eine statische Methode auf, indem Sie auf den Namen des Typs verweisen, zu dem die Methode gehört. Statische Methoden funktionieren nicht in Instanzdaten. Bei dem Versuch eine statische Methode über eine Objektinstanz aufzurufen, wird ein Compilerfehler erzeugt.

Das Aufrufen einer Methode ähnelt dem Zugreifen auf ein Feld. Fügen Sie nach dem Objektnamen (wenn Sie eine Instanzmethode aufrufen) oder dem Typnamen (beim Aufrufen einer `static`-Methode) einen Punkt, den Methodennamen und Klammern hinzu. Argumente werden innerhalb der Klammern aufgelistet und durch Kommas getrennt.

Die Methodendefinition gibt die Namen und Typen aller ggf. erforderlichen Parameter an. Wenn ein Aufrufer die Methode aufruft, werden für jeden Parameter konkrete Werte bereitgestellt, die als Argumente bezeichnet werden. Die Argumente müssen mit dem Parametertyp kompatibel sein, aber der Name des Arguments (sofern im aufzurufenden Code einer verwendet wird) muss nicht mit dem in der Methode definierten Parameternamen identisch sein. Im folgenden Beispiel enthält die `Square`-Methode einen einzelnen Parameter vom Typ `int` mit dem Namen *i*. Der erste Methodenaufruf übergibt der `Square`-Methode eine Variable vom Typ `int` mit dem Namen *num*. Der zweite übergibt eine numerische Konstante und der dritte einen Ausdruck.

[!code-csharp[csSnippets.Methods#74](../../samples/snippets/csharp/concepts/methods/params74.cs#74)]

Die häufigste Form des Methodenaufrufs verwendete Positionsargumente. Die Argumente werden in der gleichen Reihenfolge wie Methodenparameter bereitgestellt. Die Methoden der `Motorcycle`-Klasse können deshalb wie im folgenden Beispiel aufgerufen werden. Der Aufruf der `Drive`-Methode enthält z.B. zwei Argumente, die den beiden Parametern in der Syntax der Methode entsprechen. Das erste Argument wird der Wert des `miles`-Parameters, das zweite wird der Wert des `speed`-Parameters.

[!code-csharp[csSnippets.Methods#41](../../samples/snippets/csharp/concepts/methods/methods40.cs#41)]

Sie können auch *benannte Argumente* anstatt Positionsargumente verwenden, wenn Sie eine Methode aufrufen. Wenn Sie benannte Argumente verwenden, geben Sie den Parameternamen, gefolgt von einem Doppelpunkt („:“), und das Argument an. Argumente können für diese Methode in beliebiger Reihenfolge erscheinen, solange alle benötigen Argumente vorhanden sind. Im folgenden Beispiel werden die benannten Argumente zum Aufrufen der `TestMotorcycle.Drive`-Methode verwendet. In diesem Beispiel werden die benannten Argumente in umgekehrter Reihenfolge aus der Parameterliste der Methode übergeben.

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/named1.cs#45)]

Sie können eine Methode aufrufen, indem Sie sowohl Positionsargumente als auch benannte Argumente verwenden. Positionellen Argumenten können benannten Argumenten nur folgen, wenn diese an der richtigen Position verwendet werden. Im folgenden Beispiel wird die `TestMotorcycle.Drive`-Methode des vorherigen Beispiels aufgerufen, indem jeweils ein Positionsargument und ein benanntes Argument verwendet wird.

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/named2.cs#46)]

<a name="inherited"></a>

## <a name="inherited-and-overridden-methods"></a>Geerbte und überschriebene Methoden

Zusätzlich zu den Elementen, die ausdrücklich in einem Typ definiert werden, erbt ein Typ Member, die in seiner Basisklasse definiert wurden. Da alle Typen im verwalteten Typsystem direkt oder indirekt von der <xref:System.Object>-Klasse erben, erben alle Typen ihre Member, z.B. <xref:System.Object.Equals(System.Object)>, <xref:System.Object.GetType> und <xref:System.Object.ToString>. Im folgenden Beispiel wird eine `Person`-Klasse definiert, zwei `Person`-Objekte instanziiert, und es wird die `Person.Equals`-Methode aufgerufen, um zu bestimmen, ob die zwei Objekte gleich sind. Jedoch ist die `Equals`-Methode nicht in der `Person`-Klasse definiert; sie wird von <xref:System.Object> vererbt.

[!code-csharp[csSnippets.Methods#104](../../samples/snippets/csharp/concepts/methods/inherited1.cs#104)]

Typen können geerbte Member überschreiben, indem das Schlüsselwort `override` verwendet und eine Implementierung für die überschriebene Methode bereitgestellt wird. Die Signatur der Methode muss mit der überschriebenen Methode identisch sein. Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die Methode <xref:System.Object.Equals(System.Object)> überschreibt. (Sie überschreibt auch die <xref:System.Object.GetHashCode>-Methode, da die zwei Methoden konsistente Ergebnisse bereitstellen sollen)

[!code-csharp[csSnippets.Methods#105](../../samples/snippets/csharp/concepts/methods/overridden1.cs#105)]

<a name="passing"></a>

## <a name="passing-parameters"></a>Übergeben von Parametern

Typen in C# sind entweder *Werttypen* oder *Verweistypen*. Eine Liste der integrierten Werttypen finden Sie unter [Typen](./tour-of-csharp/types.md). Sowohl Werttypen als auch Verweistypen werden standardmäßig als Wert an eine Methode übergeben.

<a name="byval"></a>

### <a name="passing-parameters-by-value"></a>Übergeben von Parametern als Wert

Wenn ein Werttyp an eine Methode als Wert übergeben wird, wird anstelle des eigentlichen Objekts standardmäßig eine Kopie übergeben. Aus diesem Grund haben Änderungen am Objekt in der aufgerufenen Methode keine Auswirkung auf das ursprüngliche Objekt, wenn das Steuerelement an den Aufrufer zurückgegeben wird.

Im folgenden Beispiel wird ein Werttyp als Wert an eine Methode übergeben, und die aufgerufene Methode versucht, den Wert des Werttyps zu ändern. Es definiert eine Variable des Typs `int`, die ein Werttyp ist, initialisiert seine Werte auf 20 und übergibt ihn an eine Methode mit dem Namen `ModifyValue`, die den Wert der Variable in 30 ändert. Wenn die Methode zurückgegeben wird, bleibt der Wert der Variable jedoch unverändert.

[!code-csharp[csSnippets.Methods#10](../../samples/snippets/csharp/concepts/methods/byvalue10.cs#10)]

Wenn ein Objekt eines Verweistyps als Wert an eine Methode übergeben wird, wird ein Verweis als Wert auf das Objekt übergeben. Das heißt, die Methode erhält nicht das Objekt selbst, sondern ein Argument, das den Speicherort des Objekts angibt. Wenn Sie einen Member des Objekts unter Verwendung dieses Verweises ändern, wird die Änderung im Objekt berücksichtigt, wenn das Steuerelement der aufrufenden Methode zurückgegeben wird. Jedoch hat das Ersetzen des Objekts, das an die Methode übergeben wird, keine Auswirkung auf das ursprüngliche Objekt, wenn das Steuerelement dem Aufrufer zurückgegeben wird.

Im folgenden Beispiel wird eine Klasse (die ein Verweistyp ist) mit dem Namen `SampleRefType` definiert. Sie instanziiert ein `SampleRefType`-Objekt, weist seinem `value`-Feld 44 zu, und übergibt das Objekt der `ModifyObject`-Methode. Dieses Beispiel entspricht im Wesentlichen dem vorherigen Beispiel und übergibt ein Argument als Wert an eine Methode. Da jedoch ein Verweistyp verwendet wird, unterscheidet sich das Ergebnis. Die Änderung, die in `ModifyObject` am `obj.value`-Feld vorgenommen wurden, ändern auch das `value`-Feld des Arguments `rt` in der `Main`-Methode auf 33, wie die Ausgabe des Beispiels zeigt.

[!code-csharp[csSnippets.Methods#42](../../samples/snippets/csharp/concepts/methods/byvalue42.cs#42)]

<a name="byref"></a>

### <a name="passing-parameters-by-reference"></a>Übergeben von Parametern durch einen Verweis

Sie übergeben einen Parameter durch einen Verweis, wenn Sie den Wert eines Arguments in einer Methode ändern und diese Änderung berücksichtigen möchten, wenn die Steuerung an die aufrufende Methode zurückgegeben wird. Verwenden Sie das Schlüsselwort [`ref`](language-reference/keywords/ref.md) oder [`out`](language-reference/keywords/out-parameter-modifier.md), um einen Parameter pro Verweis zu übergeben. Außerdem können Sie einen Wert pro Verweis übergeben, um das Kopieren und Änderungen zu vermeiden, wenn Sie das Schlüsselwort [`in`](language-reference/keywords/in-parameter-modifier.md) verwenden.

Das folgende Beispiel ist identisch mit dem vorherigen Beispiel, außer dass der Wert durch einen Verweis an die `ModifyValue`-Methode übergeben wird. Wenn der Wert des Parameters in der `ModifyValue`-Methode verändert wird, wird die Wertänderung berücksichtigt, wenn das Steuerelement dem Aufrufer zurückgegeben wird.

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/byref106.cs#106)]

Ein häufiges Muster, das von ref-Parametern verwendet wird, umfasst das Tauschen der Werte der Variablen. Sie übergeben durch einen Verweis zwei Variablen an eine Methode, und die Methode tauscht deren Inhalte. Im folgenden Beispiel werden ganzzahlige Werte getauscht.

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/swap107.cs#107)]

Durch das Übergeben eines Verweistyp-Parameters können Sie den eigentlichen Wert des Verweises anstatt den Wert der einzelnen Elemente oder Felder ändern.

<a name="paramarray"></a>

### <a name="parameter-arrays"></a>Parameterarrays

Manchmal ist die Voraussetzung, dass Sie die genaue Anzahl von Argumenten für Ihre Methode angeben, restriktiv. Mithilfe des Schlüsselworts `params` wird angegeben, dass ein Parameter ein Parameterarray ist, und Sie können Ihre Methode mit einer variablen Anzahl von Argumenten aufrufen. Der mit dem Schlüsselwort `params` gekennzeichnete Parameter muss ein Arraytyp sein, und er muss der letzte Parameter in der Parameterliste der Methode sein.

Ein Aufrufer kann anschließend die Methode auf vier verschiedene Arten aufrufen:

- Durch das Übergeben eines Arrays des entsprechenden Typs, der die gewünschte Anzahl von Elementen enthält
- Durch das Übergeben einer mit Komma getrennten Liste eines einzelnen Arguments des entsprechenden Typs der Methode
- Durch Übergeben von `null`.
- Durch keine Bereitstellung eines Arguments für das Parameterarray

Das folgende Beispiel definiert eine Methode namens `GetVowels`, die alle Vokale aus einem Parameterarray zurückgibt. Die Methode `Main` zeigt alle vier Möglichkeiten zum Aufrufen der Methode. Aufrufer müssen keine Argumente für Parameter angeben, die den Modifizierer `params` enthalten. In diesem Fall ist der Parameter ein leeres Array.

[!code-csharp[csSnippets.Methods#75](~/samples/snippets/csharp/concepts/methods/params75.cs#75)]

<a name="optional"></a>

## <a name="optional-parameters-and-arguments"></a>Optionale Parameter und Argumente

Eine Methodendefinition kann angeben, dass seine Parameter erforderlich oder optional sind. Parameter sind standardmäßig erforderlich. Optionale Parameter werden einschließlich des Standardwerts des Parameters in der Methodendefinition angegeben. Wird die Methode aufgerufen, wenn kein Argument für einen optionalen Parameter angegeben wird, wird stattdessen der Standardwert verwendet.

Der Standardwert des Parameters muss von einer der folgenden Ausdrucksarten zugewiesen werden:

- Eine Konstante, z.B. eine Zeichenfolgenliteral oder eine Zahl
- Ein Ausdruck in Form von `new ValType()`, wobei `ValType` ein Werttyp ist. Beachten Sie, dass dies den impliziten parameterlosen Konstruktor des Werttyps aufruft, der eigentlich kein Member des Typs ist.
- Ein Ausdruck in Form von `default(ValType)`, wobei `ValType` ein Werttyp ist.

Wenn eine Methode erforderliche und optionale Parameter enthält, werden optionale Parameter nach allen benötigten Parametern am Ende der Parameterliste definiert.

Im folgenden Beispiel wird eine `ExampleMethod`-Methode definiert, die aus einem erforderlichen und zwei optionalen Parametern besteht.

[!code-csharp[csSnippets.Methods#21](../../samples/snippets/csharp/concepts/methods/optional1.cs#21)]

Wenn eine Methode mit mehreren optionalen Argumenten mithilfe von Positionsargumenten aufgerufen wird, muss der Aufrufer ein Argument für alle optionalen Parameter, vom ersten bis zum letzten, bereitstellen, für die ein Argument bereitgestellt wird. Bei der `ExampleMethod`-Methode muss der Parameter z.B. auch ein Argument für den `description`-Parameter bereitstellen, wenn er ein Argument für den `optionalInt`-Parameter bereitstellt. `opt.ExampleMethod(2, 2, "Addition of 2 and 2");` ist ein gültiger Methodenaufruf; `opt.ExampleMethod(2, , "Addition of 2 and 0");` erzeugt einen Compilerfehler: „Argument fehlt“.

Wenn eine Methode durch ein benanntes Argument oder einer Mischung aus benannten und Positionsargumenten aufgerufen wird, kann der Aufrufer Argumente auslassen, die dem letzten Positionsargument im Methodenaufruf folgen.

Im folgenden Beispiel wird die `ExampleMethod`-Methode dreimal aufgerufen.  Die ersten zwei Methodenaufrufe verwenden Positionsargumente. Der erste Methodenaufruf lässt beide optionale Argumente aus, während der Zweite das letzte Argument auslässt. Der dritte Methodenaufruf stellt für die benötigten Parameter ein Positionsargument bereit, verwendet aber ein benanntes Argument, um einen Wert für den `description`-Parameter bereitzustellen, während das `optionalInt`-Argument ausgelassen wird.

[!code-csharp[csSnippets.Methods#22](../../samples/snippets/csharp/concepts/methods/optional1.cs#22)]

Die Verwendung von zwei optionalen Parametern wirkt sich auf die *Überladungsauflösung* aus, oder die Art und Weise, mit der der C#-Compiler bestimmt, welche besondere Überladung von einem Methodenaufruf wie folgt aufgerufen werden sollte:

- Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.
- Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind. Ausgelassene Argumente für optionale Parameter werden ignoriert.
- Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden. Dies ist die Folge einer allgemeinen Präferenz bei der Überladungsauflösung für Kandidaten, die weniger Parameter besitzen.

<a name="return"></a>

## <a name="return-values"></a>Rückgabewerte

Methoden können einen Wert an die aufrufende Funktion (den Aufrufer) zurückgeben. Wenn der Rückgabetyp (der vor dem Methodennamen aufgeführte Typ) nicht `void` ist, kann die Methode den Wert mithilfe des `return`-Schlüsselworts zurückgeben. Eine Anweisung mit dem Schlüsselwort `return`, gefolgt von einem Wert, der dem Rückgabetyp entspricht, gibt diesen Wert an den Methodenaufrufer zurück. Methoden mit einem anderen Rückgabetyp als „void“ müssen das `return` -Schlüsselwort verwenden, um einen Wert zurückzugeben. Das `return` -Schlüsselwort beendet außerdem die Ausführung der Methode.

Wenn der Rückgabetyp `void`ist, ist eine `return` -Anweisung ohne Wert immer noch nützlich, um die Ausführung der Methode zu beenden. Ohne das `return` -Schlüsselwort wird die Ausführung der Methode beendet, wenn das Ende des Codeblocks erreicht ist.

Die folgenden beiden Methoden verwenden z. B. das `return` -Schlüsselwort, um ganze Zahlen zurückzugeben:

[!code-csharp[csSnippets.Methods#44](../../samples/snippets/csharp/concepts/methods/return44.cs#44)]

Um einen von einer Methode zurückgegebenen Wert zu verwenden, kann die aufrufende Methode den Methodenaufruf selbst an jeder Stelle verwenden, an der ein Wert des gleichen Typs ausreichend ist. Sie können den Rückgabewert auch einer Variablen zuweisen. Beispielsweise wird mit den folgenden beiden Codebeispiele das gleiche Ergebnis erzielt:

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/return44.cs#45)]

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/return44.cs#46)]

Die Verwendung einer lokalen Variablen, in diesem Fall `result`, zum Speichern eines Werts ist optional. Es kann die Lesbarkeit des Codes verbessern, oder es kann notwendig sein, wenn Sie den ursprünglichen Wert des Arguments für den gesamten Gültigkeitsbereich der Methode speichern müssen.

Manchmal möchten Sie, dass Ihre Methode mehr als einen Wert zurückgibt. Ab mit C#-7.0 können Sie dies einfach mithilfe von *Tupeltypen* und *Tupelliteralen* erledigen. Der Tupeltyp definiert die Datentypen der Elemente des Tupels. Tupelliterale stellen die tatsächlichen Werte des zurückgegebenen Tupels bereit. Im folgenden Beispiel definiert `(string, string, string, int)` den Tupeltyp, der durch die `GetPersonalInfo`-Methode zurückgegeben wird. Der `(per.FirstName, per.MiddleName, per.LastName, per.Age)`-Ausdruck ist das Tupelliteral. Die Methode gibt den ersten, mittleren und letzten Namen zusammen mit dem Alter eines `PersonInfo`-Objekts zurück.

```csharp
public (string, string, string, int) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    return (per.FirstName, per.MiddleName, per.LastName, per.Age);
}
```

Der Aufrufer kann anschließend das zurückgegebene Tupel mit Code wie dem folgenden verwenden:

```csharp
var person = GetPersonalInfo("111111111")
Console.WriteLine("{person.Item1} {person.Item3}: age = {person.Item4}");
```

Namen können auch den Tupelelementen in der Typdefinition des Tupels zugewiesen werden. Das folgende Beispiel zeigt eine alternative Version der `GetPersonalInfo`-Methode, die benannte Elemente verwendet:

```csharp
public (string FName, string MName, string LName, int Age) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    return (per.FirstName, per.MiddleName, per.LastName, per.Age);
}
```

Der vorherige Aufruf der `GetPersonInfo`-Methode kann anschließend wie folgt geändert werden:

```csharp
var person = GetPersonalInfo("111111111");
Console.WriteLine("{person.FName} {person.LName}: age = {person.Age}");
```

Wenn eine Methode einem Array als Argument übergeben wird und den Wert der einzelnen Elemente ändert, ist es nicht erforderlich, dass die Methode das Array zurückgibt, obwohl Sie sich entscheiden könnten, dies für den funktionalen Fluss von Werten oder zu stilistischen Zwecken zu tun.  Das liegt daran, dass C# alle Verweistypen als Wert übergibt und der Wert eines Arrayverweises der Zeiger auf das Array ist. Im folgenden Beispiel sind Änderungen an den Inhalten des `values`-Arrays, die in der `DoubleValues`-Methode ausgeführt werden, von jedem Code beobachtbar, der einen Verweis auf das Array hat.

[!code-csharp[csSnippets.Methods#101](../../samples/snippets/csharp/concepts/methods/returnarray1.cs#101)]

<a name="extension"></a>

## <a name="extension-methods"></a>Erweiterungsmethoden

Es gibt normalerweise zwei Möglichkeiten, einem vorhandenen Typ eine Methode hinzuzufügen:

- Ändern Sie den Quellcode für diesen Typ. Sie können dies natürlich nicht tun, wenn Sie nicht den Quellcode des Typs besitzen. Dies wird zudem eine bahnbrechende Änderung, wenn Sie auch private Datenfelder zur Unterstützung der Methode hinzufügen.
- Definieren Sie die neue Methode in einer abgeleiteten Klasse. Eine Methode kann nicht auf diese Weise für andere Typen wie Strukturen oder Enumerationen mithilfe von Vererbung hinzugefügt werden. Sie kann auch nicht verwendet werden, um einer versiegelten Klasse eine Methode „hinzuzufügen“.

Erweiterungsmethoden lassen Sie eine Methode einem vorhanden Typ „hinzufügen“, ohne den eigentlichen Typ zu verändern oder die neue Methode in einem geerbten Typ zu implementieren. Die Erweiterungsmethode muss sich auch nicht im gleichen Assembly wie der Typ befinden, den es erweitert. Sie rufen eine Erweiterungsmethode auf, als ob es sich um einen definierten Member eines Typs handele.

Weitere Informationen finden Sie unter [Erweiterungsmethoden](programming-guide/classes-and-structs/extension-methods.md).

<a name="async"></a>

## <a name="async-methods"></a>Asynchrone Methoden

Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Methoden oder Lambda-Ausdrücke teilen zu müssen.

Wenn Sie eine Methode mit dem Modifizierer [async](language-reference/keywords/async.md) kennzeichnen, können Sie den Operator [await](language-reference/operators/await.md) in der Methode verwenden. Wenn ein `await`-Ausdruck in der asynchronen Methode erreicht wird, wird die Steuerung an den Aufrufer zurückgegeben, wenn die erwartete Aufgabe nicht fertig ist, und die Ausführung der Methode mit dem Schlüsselwort `await` wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Methode fortgesetzt werden.

> [!NOTE]
> Eine asynchrone Methode wird an den Aufrufer zurückgegeben, wenn sie entweder auf das erste erwartete Objekt trifft, das noch nicht abgeschlossen wurde, oder das Ende der asynchronen Methode erreicht.

Eine asynchrone Methode kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> oder `void` haben. Der Rückgabetyp `void` wird hauptsächlich zum Definieren von Ereignishandlern verwendet, wobei ein `void`-Rückgabetyp erforderlich ist. Auf eine asynchrone Methode, die `void` zurückgibt, kann nicht gewartet werden, und der Aufrufer einer Methode mit void-Rückgabe kann keine Ausnahmen abfangen, die die Methode auslöst. Ab C# 7.0 kann eine asynchrone Methode [jeden Task-ähnlichen Typ zurückgeben](./whats-new/csharp-7.md#generalized-async-return-types).

Im folgenden Beispiel ist `DelayAsync` eine asynchrone Methode, die eine Rückgabeanweisung besitzt, die eine ganze Zahl zurückgibt. Da es sich um eine async-Methode handelt, muss die Methodendeklaration einen `Task<int>`-Rückgabetyp haben. Da der Rückgabetyp `Task<int>` ist, ergibt die Auswertung des `await`-Ausdrucks in `DoSomethingAsync` eine ganze Zahl, wie die folgende `int result = await delayTask`-Anweisung veranschaulicht.

:::code language="csharp" source="programming-guide/classes-and-structs/snippets/classes-and-structs/methods/Program.cs":::

Mit einer asynchronen Methode können keine [in](language-reference/keywords/in-parameter-modifier.md)-, [ref](language-reference/keywords/ref.md)- oder [out](language-reference/keywords/out-parameter-modifier.md)-Parameter deklariert, jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.

 Weitere Informationen zu den asynchronen Methoden finden Sie unter [Asynchrone Programmierung mit async und await](async.md) und [Asynchrone Rückgabetypen (C#)](programming-guide/concepts/async/async-return-types.md).

<a name="expr"></a>

## <a name="expression-bodied-members"></a>Ausdruckskörpermember

Es gibt häufig Methodendefinitionen, die einfach direkt das Ergebnis eines Ausdrucks zurückgeben oder eine einzige Anweisung als Text der Methode aufweisen.  Es ist eine Syntaxabkürzung zur Definition solcher Methoden mithilfe von `=>`verfügbar:

```csharp
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);
public void Print() => Console.WriteLine(First + " " + Last);
// Works with operators, properties, and indexers too.
public static Complex operator +(Complex a, Complex b) => a.Add(b);
public string Name => First + " " + Last;
public Customer this[long id] => store.LookupCustomer(id);
```

Wenn die Methode `void` zurückgibt oder es sich um eine asynchrone Methode handelt, muss der Text der Methode ein Anweisungsausdruck sein (wie bei Lambdas).  Eigenschaften und Indexer müssen schreibgeschützt sein. Verwenden Sie darüber hinaus nicht das `get`-Accessorschlüsselwort.

<a name="iterators"></a>

## <a name="iterators"></a>Iterators

Ein Iterator führt eine benutzerdefinierte Iteration durch eine Auflistung durch, z. B. eine Liste oder ein Array. Ein Iterator verwendet die [yield return](language-reference/keywords/yield.md) -Anweisung, um jedes Element einzeln nacheinander zurückzugeben. Wenn eine `yield return`-Anweisung erreicht wird, wird die aktuelle Position gespeichert, sodass der Aufrufer das nächste Element in der Sequenz anfordern kann.

Der Rückgabetyp eines Iterators kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.

Weitere Informationen finden Sie unter [Iteratoren](programming-guide/concepts/iterators.md).

## <a name="see-also"></a>Weitere Informationen

- [Zugriffsmodifizierer](language-reference/keywords/access-modifiers.md)
- [Statische Klassen und statische Klassenmember](programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [Vererbung](programming-guide/classes-and-structs/inheritance.md)
- [Abstrakte und versiegelte Klassen und Klassenmember](programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [params](language-reference/keywords/params.md)
- [out](language-reference/keywords/out-parameter-modifier.md)
- [ref](language-reference/keywords/ref.md)
- [in](language-reference/keywords/in-parameter-modifier.md)
- [Übergeben von Parametern](programming-guide/classes-and-structs/passing-parameters.md)
