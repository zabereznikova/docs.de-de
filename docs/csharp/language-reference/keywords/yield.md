---
title: 'Kontextabhängiges yield-Schlüsselwort: C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: ec1058d1590d64fa8d8786b3118ecf9733c55d6f
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063145"
---
# <a name="yield-c-reference"></a>yield (C#-Referenz)

Wenn Sie das [kontextabhängige Schlüsselwort](index.md#contextual-keywords) `yield` in einer Anweisung verwenden, geben Sie damit an, dass die Methode, der Operator oder der `get`-Accessor, in der bzw. dem es vorkommt, ein Iterator ist. Wird ein Iterator mithilfe von `yield` definiert, ist eine explizite zusätzliche Klasse (die Klasse, die den Zustand für eine Enumeration enthält, siehe beispielsweise <xref:System.Collections.Generic.IEnumerator%601>) nicht erforderlich, wenn Sie das <xref:System.Collections.IEnumerable>-Muster und das <xref:System.Collections.IEnumerator>-Muster für einen benutzerdefinierten Auflistungstyp implementieren.

Im folgenden Beispiel werden zwei Formen der `yield`-Anweisung gezeigt.

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a>Hinweise

Sie verwenden eine `yield return`-Anweisung, um jedes Element einzeln zurückzugeben.

Die von einer Iteratormethode zurückgegebene Sequenz kann durch eine [foreach](foreach-in.md)-Anweisung oder eine LINQ-Abfrage verwendet werden. Jede Iteration der `foreach`-Schleife ruft die Iteratormethode auf. Wenn eine `yield return`-Anweisung im Iterator erreicht wird, wird ein `expression`-Ausdruck zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Sie verwenden eine `yield break`-Anweisung, um die Iteration zu beenden.

Weitere Informationen zu Iteratoren finden Sie unter [Iterators (Iteratoren)](../../iterators.md).

## <a name="iterator-methods-and-get-accessors"></a>Iteratormethoden und Get-Zugriffsmethoden

Die Deklaration eines Iterators muss die folgenden Anforderungen erfüllen:

- Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.

- Die Deklaration darf nicht über [in](in-parameter-modifier.md)-, [ref](ref.md)- oder [out](out-parameter-modifier.md)-Parameter verfügen.

Der `yield`-Typ eines Iterators, der <xref:System.Collections.IEnumerable> oder <xref:System.Collections.IEnumerator> zurückgibt, ist `object`.  Wenn der Iterator <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Collections.Generic.IEnumerator%601> zurückgibt, ist eine implizite Konvertierung vom Typ des Ausdrucks in der `yield return`-Anweisung in den generischen Typparameter erforderlich.

Folgendes darf keine `yield return`- oder `yield break`-Anweisung enthalten:

- [Lambdaausdrücke](../operators/lambda-expressions.md) und [anonyme Methoden](../operators/delegate-operator.md).

- Methoden, die unsichere Blöcke enthalten. Weitere Informationen finden Sie unter [unsafe](unsafe.md).

## <a name="exception-handling"></a>Ausnahmebehandlung

Eine `yield return`-Anweisung kann sich nicht in einem try-catch-Block befinden. Eine `yield return`-Anweisung kann sich im try-Block einer try-finally-Anweisung befinden.

Eine `yield break`-Anweisung kann sich in einem try- oder catch-Block befinden, nicht jedoch in einem finally-Block.

Wenn der `foreach`-Text (außerhalb der Iteratormethode) eine Ausnahme auslöst, wird ein `finally`-Block in der Iteratormethode ausgeführt.

## <a name="technical-implementation"></a>Technische Implementierung

Der folgende Code gibt einen `IEnumerable<string>` aus einer Iteratormethode zurück und durchläuft dann die Elemente.

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

Der Aufruf von `MyIteratorMethod` führt nicht den Text der Methode aus. Stattdessen gibt der Aufruf einen `IEnumerable<string>` in die Variable `elements` zurück.

Bei einer Iteration der `foreach`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen. Dieser Aufruf führt `MyIteratorMethod` aus, bis die nächste `yield return`-Anweisung erreicht ist. Der Ausdruck, der durch die `yield return`-Anweisung zurückgegeben wird, ermittelt nicht nur den Wert der `element`-Variable für die Verwendung im Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A>-Eigenschaft von `elements` (ein `IEnumerable<string>`).

Bei jeder nachfolgenden Iteration der `foreach`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `yield return`-Anweisung. Die `foreach`-Schleife wird beendet, wenn das Ende der Iteratormethode oder eine `yield break`-Anweisung erreicht wird.

## <a name="example"></a>Beispiel

Das folgende Beispiel weist eine `yield return`-Anweisung auf, die sich innerhalb einer `for`-Schleife befindet. Jede Iteration des `foreach`-Anweisungstexts in der Methode `Main` erzeugt einen Aufruf an die Iteratorfunktion `Power`. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `yield return`-Schleife zur nächsten Ausführung der `for`-Anweisung.

Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.IEnumerable>, was ein Iteratorschnittstellentyp ist. Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt einen `get`-Accessor, der ein Iterator ist. Im Beispiel gibt jede `yield return`-Anweisung eine Instanz einer benutzerdefinierten Klasse zurück.

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [foreach, in](foreach-in.md)
- [Iteratoren](../../iterators.md)
