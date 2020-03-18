---
title: Methoden – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#]
- C# language, methods
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
ms.openlocfilehash: 114fa2973c50be9a4199db9729e3cd9ea6122866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626528"
---
# <a name="methods-c-programming-guide"></a>Methoden (C#-Programmierhandbuch)

Eine Methode ist ein Codeblock, der eine Reihe von Anweisungen enthält. Ein Programm bewirkt die Ausführung der Anweisungen, indem die Methode aufgerufen wird und alle erforderlichen Methodenargumente angegeben werden. In C# werden alle Anweisungen im Kontext einer Methode ausgeführt. Die Methode `Main` ist der Einstiegspunkt jeder C#-Anwendung und wird beim Start des Programms von der Common Language Runtime (CLR) aufgerufen.

> [!NOTE]
> In diesem Artikel werden benannte Methoden erläutert. Informationen über anonyme Funktionen finden Sie unter [Anonyme Funktionen](../statements-expressions-operators/anonymous-functions.md).

## <a name="method-signatures"></a>Methodensignaturen

Methoden werden in einer [Klasse](../../language-reference/keywords/class.md), [Struktur](../../language-reference/builtin-types/struct.md) oder [Schnittstelle](../interfaces/index.md) deklariert, indem die Zugriffsebene wie z. B. `public` oder `private`, optionale Modifizierer wie z. B. `abstract` oder `sealed`, der Rückgabewert, der Name der Methode und die Methodenparameter angegeben werden. Diese Teile bilden zusammen die Signatur der Methode.

> [!NOTE]
> Ein Rückgabetyp einer Methode ist nicht Teil der Signatur der Methode, wenn es um die Methodenüberladung geht. Er ist jedoch Teil der Methodensignatur, wenn die Kompatibilität zwischen einem Delegaten und der Methode bestimmt wird, auf die dieser verweist.

Methodenparameter werden in Klammern eingeschlossen und durch Kommas getrennt. Leere Klammern geben an, dass für die Methode keine Parameter erforderlich sind. Diese Klasse enthält vier Methoden:

[!code-csharp[csProgGuideObjects#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#40)]

## <a name="method-access"></a>Methodenzugriff

Das Aufrufen einer Methode für ein Objekt ähnelt dem Zugreifen auf ein Feld. Fügen Sie nach dem Objektnamen einen Punkt, den Namen der Methode und Klammern hinzu. Argumente werden innerhalb der Klammern aufgelistet und durch Kommas getrennt. Die Methoden der `Motorcycle` -Klasse können also wie im folgenden Beispiel gezeigt aufgerufen werden:

[!code-csharp[csProgGuideObjects#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#41)]

## <a name="method-parameters-vs-arguments"></a>Methodenparameter und Argumente

Die Methodendefinition gibt die Namen und Typen aller ggf. erforderlichen Parameter an. Wenn aufrufender Code die Methode aufruft, werden für jeden Parameter konkrete Werte bereitgestellt, die als Argumente bezeichnet werden. Die Argumente müssen mit dem Parametertyp kompatibel sein, aber der im aufrufenden Code verwendete Name des Arguments (sofern vorhanden) muss nicht mit dem in der Methode definierten Parameternamen identisch sein. Beispiel:

[!code-csharp[csProgGuideObjects#74](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#74)]

## <a name="passing-by-reference-vs-passing-by-value"></a>Übergeben nach Verweis und Übergeben nach Wert

Wenn eine Instanz eines [Werttyps](../../language-reference/builtin-types/value-types.md) an eine Methode übergeben wird, wird standardmäßig die zugehörige Kopie anstelle der Instanz selbst übermittelt. Änderungen am Argument haben daher keine Auswirkungen auf die originale Instanz in der aufrufenden Methode. Verwenden Sie das Schlüsselwort `ref`, um eine Werttypinstanz als Verweis zu übergeben. Weitere Informationen finden Sie unter [Übergeben von Werttypparametern](./passing-value-type-parameters.md).

Wenn ein Objekt eines Verweistyps an eine Methode übergeben wird, wird ein Verweis auf das Objekt übergeben. Das heißt, die Methode erhält nicht das Objekt selbst, sondern ein Argument, das den Speicherort des Objekts angibt. Wenn Sie einen Member des Objekts unter Verwendung dieses Verweises ändern, wird die Änderung im Argument in der aufrufenden Methode berücksichtigt, selbst wenn Sie das Objekt als Wert übergeben.

Sie erstellen einen Verweistyp mithilfe des `class`-Schlüsselworts, wie im folgenden Beispiel gezeigt:

[!code-csharp[csProgGuideObjects#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#42)]

Wenn Sie jetzt ein Objekt, das auf diesem Typ basiert, an eine Methode übergeben, wird ein Verweis auf das Objekt übergeben. Das folgende Beispiel übergibt ein Objekt des `SampleRefType`-Typs an die `ModifyObject`-Methode:

[!code-csharp[csProgGuideObjects#75](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#75)]

Das Beispiel entspricht im Wesentlichen dem vorherigen Beispiel und übergibt ein Argument als Wert an eine Methode. Aber da ein Verweistyp verwendet wird, unterscheidet sich das Ergebnis. Die Änderung, die in `ModifyObject` am `value` -Feld des Parameters ( `obj`) vorgenommen wird, ändert auch das `value` -Feld des Arguments ( `rt`) in der `TestRefType` -Methode. Die `TestRefType` -Methode zeigt 33 als Ausgabe an.

Weitere Informationen zum Übergeben von Verweistypen als Verweis oder als Wert finden Sie unter [Übergeben von Verweistypparametern ](./passing-reference-type-parameters.md) und [Verweistypen](../../language-reference/keywords/reference-types.md).

## <a name="return-values"></a>Rückgabewerte

Methoden können einen Wert an die aufrufende Funktion (den Aufrufer) zurückgeben. Wenn der Rückgabetyp – der vor dem Methodennamen aufgeführte Typ – nicht `void`ist, kann die Methode den Wert mithilfe des `return` -Schlüsselworts zurückgeben. Eine Anweisung mit der `return` -Schlüsselwort, gefolgt von einem Wert, der dem Rückgabetyp entspricht, gibt diesen Wert an den Methodenaufrufer zurück.

Der Wert kann an den Aufrufer nach Wert oder, ab C# 7.0, [nach Verweis](ref-returns.md) zurückgegeben werden. Werte werden an den Aufrufer nach Verweis zurückgegeben, wenn das Schlüsselwort `ref` in der Methodensignatur verwendet wird und auf jedes `return`-Schlüsselwort folgt. Die folgende Methodensignatur und Rückgabeanweisung geben an, dass die Methode eine Variable mit dem Namen `estDistance` nach Verweis an den Aufrufer zurückgibt.

```csharp
public ref double GetEstimatedDistance()
{
    return ref estDistance;
}
```

Das `return` -Schlüsselwort beendet außerdem die Ausführung der Methode. Wenn der Rückgabetyp `void`ist, ist eine `return` -Anweisung ohne Wert immer noch nützlich, um die Ausführung der Methode zu beenden. Ohne das `return` -Schlüsselwort wird die Ausführung der Methode beendet, wenn das Ende des Codeblocks erreicht ist. Methoden mit einem anderen Rückgabetyp als „void“ müssen das `return` -Schlüsselwort verwenden, um einen Wert zurückzugeben. Die folgenden beiden Methoden verwenden z. B. das `return` -Schlüsselwort, um ganze Zahlen zurückzugeben:

[!code-csharp[csProgGuideObjects#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#44)]

Um einen von einer Methode zurückgegebenen Wert zu verwenden, kann die aufrufende Methode den Methodenaufruf selbst an jeder Stelle verwenden, an der ein Wert des gleichen Typs ausreichend ist. Sie können den Rückgabewert auch einer Variablen zuweisen. Beispielsweise wird mit den folgenden beiden Codebeispiele das gleiche Ergebnis erzielt:

[!code-csharp[csProgGuideObjects#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#45)]

[!code-csharp[csProgGuideObjects#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#46)]

Die Verwendung einer lokalen Variablen, in diesem Fall `result`, zum Speichern eines Werts ist optional. Es kann die Lesbarkeit des Codes verbessern, oder es kann notwendig sein, wenn Sie den ursprünglichen Wert des Arguments für den gesamten Gültigkeitsbereich der Methode speichern müssen.

Um einen Wert zu verwenden, der nach Verweis von einer Methode zurückgegeben wurde, müssen Sie die Variable [ref local](ref-returns.md#ref-locals) deklarieren, wenn Sie diesen Wert modifizieren möchten. Wenn die `Planet.GetEstimatedDistance`-Methode z.B. einen <xref:System.Double>-Wert nach Verweis zurückgibt, können Sie ihn mit Code wie dem folgenden als ref local-Variable definieren:

```csharp
ref int distance = plant
```

Die Zurückgabe eines mehrdimensionalen Arrays aus einer Methode, `M`, die den Inhalt eines Arrays modifiziert, ist nicht vonnöten, wenn die aufrufende Funktion das Array an `M` übergeben hat.  Sie können das resultierende Array aus `M` für den funktionalen Fluss der Werte oder aus stilistischen Gründen zurückgeben. Dies ist jedoch nicht nötig, da C# alle Referenztypen nach Wert übergibt und der Wert eines Arrayverweises ein Zeiger auf das Array ist. In der Methode `M` werden Änderungen am Inhalt des Arrays durch jeden Code berücksichtigt, der einen Verweis auf das Array enthält, wie im folgenden Beispiel gezeigt:

```csharp
static void Main(string[] args)
{
    int[,] matrix = new int[2, 2];
    FillMatrix(matrix);
    // matrix is now full of -1
}

public static void FillMatrix(int[,] matrix)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(1); j++)
        {
            matrix[i, j] = -1;
        }
    }
}
```

Weitere Informationen finden Sie unter [return](../../language-reference/keywords/return.md).

## <a name="async-methods"></a>Asynchrone Methoden

Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Methoden oder Lambda-Ausdrücke teilen zu müssen.

Wenn Sie eine Methode mit dem [async](../../language-reference/keywords/async.md) -Modifizierer kennzeichnen, können Sie den [await](../../language-reference/operators/await.md) Operator in der Methode verwenden. Wenn ein await-Ausdruck in der asynchronen Methode erreicht wird, wird die Steuerung an den Aufrufer zurückgegeben, und die Ausführung der Methode wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Methode fortgesetzt werden.

> [!NOTE]
> Eine asynchrone Methode wird an den Aufrufer zurückgegeben, wenn sie entweder auf das erste erwartete Objekt trifft, das noch nicht abgeschlossen wurde, oder das Ende der asynchronen Methode erreicht.

Eine asynchrone Methode kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>oder „void“ haben. Der void-Rückgabetyp wird hauptsächlich zum Definieren von Ereignishandlern verwendet, bei denen ein void-Rückgabetyp erforderlich ist. Auf eine asynchrone Methode, die „void“ zurückgibt, kann nicht gewartet werden, und der Aufrufer einer Methode mit void-Rückgabe kann keine Ausnahmen auffangen, die die Methode auslöst.

Im folgenden Beispiel ist `DelayAsync` eine asynchrone Methode mit dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>. `DelayAsync` enthält eine `return` -Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund muss die Methodendeklaration von `DelayAsync` den Rückgabetyp `Task<int>`haben. Da der Rückgabetyp `Task<int>`ist, ergibt die Auswertung des `await` -Ausdrucks in `DoSomethingAsync` eine ganze Zahl, wie die folgende Anweisung veranschaulicht: `int result = await delayTask`.

Die `startButton_Click` -Methode ist ein Beispiel für eine asynchrone Methode mit void-Rückgabetyp. Da `DoSomethingAsync` eine asynchrone Methode ist, muss die Aufgabe für den Aufruf von `DoSomethingAsync` abgewartet werden, wie in der folgenden Anweisung dargestellt: `await DoSomethingAsync();`. Die `startButton_Click` -Methode muss mit dem `async` -Modifizierer definiert werden, da die Methode über einen `await` -Ausdruck verfügt.

[!code-csharp[csAsyncMethod#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncmethod/cs/mainwindow.xaml.cs#2)]

Mit einer asynchronen Methode können keine [ref](../../language-reference/keywords/ref.md)- oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter deklariert, jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.

Weitere Informationen über asynchrone Methoden finden Sie unter [Asynchronous Programming with async and await (Asynchrone Programmierung mit Async und Await)](../concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../concepts/async/control-flow-in-async-programs.md) und [Asynchrone Rückgabetypen](../concepts/async/async-return-types.md).

## <a name="expression-body-definitions"></a>Ausdruckstextdefinitionen

Es gibt häufig Methodendefinitionen, die einfach direkt das Ergebnis eines Ausdrucks zurückgeben oder eine einzige Anweisung als Text der Methode aufweisen. Es ist eine Syntaxabkürzung zur Definition solcher Methoden mithilfe von `=>`verfügbar:

```csharp
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);
public void Print() => Console.WriteLine(First + " " + Last);
// Works with operators, properties, and indexers too.
public static Complex operator +(Complex a, Complex b) => a.Add(b);
public string Name => First + " " + Last;
public Customer this[long id] => store.LookupCustomer(id);
```

Wenn die Methode `void` zurückgibt oder es sich um eine asynchrone Methode handelt, muss der Text der Methode ein Anweisungsausdruck sein (wie bei Lambdas). Eigenschaften und Indexer müssen schreibgeschützt sein. Verwenden Sie darüber hinaus nicht das `get`-Accessorschlüsselwort.

## <a name="iterators"></a>Iterators

Ein Iterator führt eine benutzerdefinierte Iteration durch eine Auflistung durch, z. B. eine Liste oder ein Array. Ein Iterator verwendet die Anweisung [yield return](../../language-reference/keywords/yield.md), um jedes Element einzeln nacheinander zurückzugeben. Wenn eine [yield return](../../language-reference/keywords/yield.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Sie rufen einen Iterator im Clientcode mithilfe einer [foreach](../../language-reference/keywords/foreach-in.md) Anweisung auf.

Der Rückgabetyp eines Iterators kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.

Weitere Informationen finden Sie unter [Iteratoren](../concepts/iterators.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](index.md)
- [Zugriffsmodifizierer](access-modifiers.md)
- [Statische Klassen und statische Klassenmember](static-classes-and-static-class-members.md)
- [Vererbung](inheritance.md)
- [Abstrakte und versiegelte Klassen und Klassenmember](abstract-and-sealed-classes-and-class-members.md)
- [params](../../language-reference/keywords/params.md)
- [return](../../language-reference/keywords/return.md)
- [out](../../language-reference/keywords/out.md)
- [ref](../../language-reference/keywords/ref.md)
- [Übergeben von Parametern](passing-parameters.md)
