---
title: if-else – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 61b60674d3b5de4649a52d2a165265ae0a27e0be
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738852"
---
# <a name="if-else-c-reference"></a>if-else (C#-Referenz)

Eine `if` -Anweisung ermittelt, welche Anweisung basierend auf dem Wert eines booleschen Ausdrucks auszuführen ist. Im folgenden Beispiel wird die `bool` Variable `condition` auf `true` festgelegt und dann in der `if` Anweisung überprüft. Die Ausgabe lautet `The variable is set to true.`.

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

Die können die Beispiele in diesem Thema ausführen, indem Sie sie in die `Main` -Methode einer Konsolenanwendung platzieren.

Eine `if` -Anweisung in C# kann zwei Formen annehmen, wie im folgenden Beispiel gezeigt.

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

In einer `if-else` -Anweisung wird, wenn `condition` zu true ausgewertet wird, `then-statement` ausgeführt. Wenn `condition` false ist, wird `else-statement` ausgeführt. Da `condition` nicht gleichzeitig true und false sein kann, können `then-statement` und `else-statement` einer `if-else` -Anweisung niemals beide ausgeführt werden. Nachdem `then-statement` oder `else-statement` ausgeführt wurde, wird die Steuerung an die `if` -Anweisung übergeben.

In einer `if` -Anweisung, die keine `else` -Anweisung enthält, wird, wenn `condition` true ist, `then-statement` ausgeführt. Wenn `condition` false ist, wird die Steuerung an die nächste Anweisung nach der `if` Anweisung übergeben.

Sowohl `then-statement` als auch `else-statement` können aus einer einzelnen Anweisung oder mehreren in Klammern eingeschlossenen Anweisungen bestehen (`{}`). Bei einer Anweisung sind die Klammern optional, sie werden aber empfohlen.

Die Anweisung bzw. die Anweisungen in `then-statement` und `else-statement` können von einer beliebigen Art sein und eine weitere `if` Anweisung enthalten, die in der ursprünglichen `if` -Anweisung geschachtelt ist. In geschachtelten `if` Anweisungen gehört jede `else` -Klausel zur letzten `if` -Anweisung, die nicht über eine zugehörige `else`-Anweisung verfügt. Im folgenden Beispiel wird `Result1` angezeigt, wenn `m > 10` und `n > 20` zu true ausgewertet werden. Wenn `m > 10` true ist, `n > 20` hingegen false, wird `Result2` angezeigt.

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

Wenn stattdessen `Result2` angezeigt werden soll, wenn `(m > 10)` false ist, können Sie diese Zuordnung mithilfe von Klammern festlegen, um den Beginn und das Ende der geschachtelten `if` Anweisung anzugeben, wie im folgenden Beispiel gezeigt.

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

`Result2` wird angezeigt, wenn die Bedingung `(m > 10)` als FALSE ausgewertet wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel geben Sie ein Zeichen über die Tastatur ein. Das Programm verwendet eine geschachtelte `if` -Anweisung, um zu bestimmen, ob das eingegebene Zeichen ein alphabetisches Zeichen ist. Wenn das eingegebene Zeichen ein alphabetisches Zeichen ist, überprüft das Programm, ob das eingegebene Zeichen in Groß- oder in Kleinschreibung ist. In beiden Fällen wird eine Meldung angezeigt.

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a>Beispiel

Sie können eine `if` Anweisung auch in einem else-Block schachteln, wie der folgende Codeausschnitt zeigt. Im Beispiel werden `if` Anweisungen in zwei else-Blocks und einem then-Block geschachtelt. In den Kommentaren ist angegeben, welche Bedingungen in jedem Block true oder false sind.

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird bestimmt, ob ein eingegebenes Zeichen ein Kleinbuchstabe, ein Großbuchstabe oder eine Zahl ist. Wenn alle drei Bedingungen false sind, ist das Zeichen kein alphanumerisches Zeichen. Das Beispiel zeigt für jeden Fall eine Meldung an.

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

So, wie eine Anweisung im else-Block oder then-Block jede beliebige Anweisung sein kann, können Sie für die Bedingungen einen beliebigen gültigen booleschen Ausdruck verwenden. Sie können [logische Operatoren](../operators/boolean-logical-operators.md) wie `!`, `&&`, `||`, `&`, `|` und `^` verwenden, um Verbundbedingungen zu erstellen. Der folgende Code enthält Beispiele.

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [?: Operator](../operators/conditional-operator.md)
- [if-else-Anweisung (C++)](/cpp/cpp/if-else-statement-cpp)
- [switch](switch.md)
