---
title: throw – C#-Referenz
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
ms.openlocfilehash: 7ed84e04dae54283e4b5f03be0600c4dbf95b4b4
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063119"
---
# <a name="throw-c-reference"></a>throw (C#-Referenz)

Signalisiert das Auftreten einer Ausnahme während der Programmausführung.  
  
## <a name="remarks"></a>Hinweise

Die Syntax von `throw` lautet:

```csharp
throw [e];
```

Wo `e` eine Instanz einer Klasse ist, die von <xref:System.Exception?displayProperty=nameWithType> abgeleitet wird. Im folgenden Beispiel wird die `throw`-Anweisung verwendet, um eine <xref:System.IndexOutOfRangeException> auszulösen, wenn das Argument, das an eine Methode mit dem Namen `GetNumber` übergeben wurde, nicht auf einen gültigen Index eines internen Arrays reagiert.

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

Methodenaufrufer verwenden anschließend einen `try-catch`- oder `try-catch-finally`-Block, um die ausgelöste Ausnahme zu behandeln. Im folgenden Beispiel wird die Ausnahme behandelt, die von der Methode `GetNumber` ausgelöst wurde.

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a>Erneutes Auslösen einer Ausnahme

`throw` kann auch in einem `catch`-Block verwendet werden, um eine Ausnahme erneut auszulösen, die in einem `catch`-Block behandelt wurde.  In diesem Fall verwendet `throw` keinen Operanden für die Ausnahme. Es ist besonders hilfreich, wenn eine Methode ein Argument in einer aufrufenden Funktion an eine andere Bibliotheksmethode übergibt, und die Bibliotheksmethode eine Ausnahme auslöst, die an den Aufrufer übergeben werden muss. Im folgenden Beispiel wird z.B. eine <xref:System.NullReferenceException> erneut ausgelöst, die beim Versuch, das erste Zeichen einer deinitialisierten Zeichenfolge abzurufen, ausgelöst wird.

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> Sie können auch die `throw e`-Syntax in einem `catch`-Block verwenden, um eine neue Ausnahme zu instanziieren, die Sie an den Aufrufer übergeben. In diesem Fall wird die Stapelüberwachung der ursprünglichen Ausnahme, die von der Eigenschaft <xref:System.Exception.StackTrace> abrufbar ist, nicht beibehalten.

## <a name="the-throw-expression"></a>Der `throw`-Ausdruck

Ab C# 7.0 kann `throw` sowohl als Ausdruck als auch als Anweisung verwendet werden. Dadurch wird eine Ausnahme in Kontexten ausgelöst, die zuvor nicht unterstützt wurden. Dazu gehören:

- [Der bedingte Operator](../operators/conditional-operator.md). Im folgenden Beispiel wird ein `throw`-Ausdruck verwendet, um eine <xref:System.ArgumentException> auszulösen, wenn eine Methode an ein leeres Zeichenfolgenarray übergeben wird. Diese Logik müsste vor C# 7.0 in einer `if`/`else`-Anweisung erscheinen.

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- [Der NULL-Sammeloperator](../operators/null-coalescing-operator.md). Im folgenden Beispiel wird eine `throw`-Anweisung mit einem NULL-Sammeloperator verwendet, um eine Ausnahme auszulösen, wenn die Zeichenfolge, die einer Eigenschaft `Name` zugewiesen wurde, `null` ist.

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- Ein Ausdruckskörper[lambda](../operators/lambda-expressions.md) oder eine Ausdruckskörpermethode. Das folgende Beispiel veranschaulicht eine Ausdruckskörpermethode, die eine <xref:System.InvalidCastException> auslöst, da eine Konvertierung in einen <xref:System.DateTime>-Wert nicht unterstützt wird.

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [try-catch](try-catch.md)
- [C#-Schlüsselwörter](index.md)
- [Vorgehensweise: Explizites Auslösen von Ausnahmen](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
