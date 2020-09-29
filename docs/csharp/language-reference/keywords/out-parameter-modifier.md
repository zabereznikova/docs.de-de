---
description: Modifizierer für out-Parameter – C#-Verweis
title: Modifizierer für out-Parameter – C#-Verweis
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 6addfa3a654c0bb4e10213a3fb4fc0368f2570b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200185"
---
# <a name="out-parameter-modifier-c-reference"></a>Modifizierer für out-Parameter (C#-Verweis)

Das Schlüsselwort `out` bewirkt, dass Argumente per Verweis übergeben werden. Es stellt den formalen Parameter als Alias für das Argument dar, das eine Variable sein muss. Anders ausgedrückt, jede Operation mit dem Parameter wird mit dem Argument durchgeführt. Dies entspricht dem Schlüsselwort [ref](ref.md), mit Ausnahme davon, dass bei `ref` die Variable initialisiert sein muss, bevor sie übergeben wird. Es ähnelt auch dem Schlüsselwort [in](in-parameter-modifier.md). Allerdings lässt `in` nicht zu, dass die aufgerufene Methode den Argumentwert verändern kann. Um einen Parameter `out` zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode das Schlüsselwort `out` explizit verwenden. Zum Beispiel:  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> Das Schlüsselwort `out` kann auch mit einem generischen Typparameter verwendet werden, um anzugeben, dass der Typparameter kovariant ist. Weitere Informationen zur Verwendung des Schlüsselworts `out` in diesem Kontext finden Sie unter [out (generischer Modifizierer)](out-generic-modifier.md).
  
Variablen, die als `out`-Argumente übergeben wurden, müssen nicht initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden. Die aufgerufene Methode ist jedoch erforderlich, um einen Wert zuzuweisen, bevor die Methode zurückgegeben wird.  
  
Die Schlüsselwörter `in`, `ref` und `out` werden nicht als Teil der Methodensignatur zum Zwecke der Überladungsauflösung betrachtet. Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument. Der folgende Code wird z. B. nicht kompiliert:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Überladen ist zwar legal, wenn jedoch eine Methode ein `ref`-, `in`- oder `out`-Argument übernimmt und die andere über keinen dieser Modifizierer verfügt, gilt Folgendes:  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

Der Compiler wählt die beste Überladung aus, indem er die Parametermodifizierer auf der Aufrufsite den im Methodenaufruf verwendeten Parametermodifizierern zuordnet.

Eigenschaften sind keine Variablen und können daher nicht als `out`-Parameter übergeben werden.
  
Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:  
  
- Asynchrone Methoden, die Sie mit dem [async](./async.md)-Modifizierer definieren.  
  
- Iterator-Methoden, die eine [yield return](./yield.md)- oder `yield break`-Anweisung enthalten.  

Für [Erweiterungsmethoden](../../programming-guide/classes-and-structs/extension-methods.md) gelten die folgenden Einschränkungen:

- Das `out`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden.
- Das `ref`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden, wenn es sich bei dem Argument nicht um eine Struktur handelt oder ein generischer Typ nicht auf eine Struktur beschränkt ist.
- Das `in`-Schlüsselwort kann nur verwendet werden, wenn das erste Argument eine Struktur ist. Das `in`-Schlüsselwort kann nicht für einen generischen Typ verwendet werden – selbst bei einer Beschränkung auf eine Struktur.

## <a name="declaring-out-parameters"></a>Deklarieren eines `out`-Parameters

Das Deklarieren einer Methode mit `out`-Argumenten ist eine gängige Methode, um mehrere Werte zurückzugeben. Ab C# 7.0 sollten Sie [Werttupel](../builtin-types/value-tuples.md) für ähnliche Szenarien berücksichtigen. Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben. Das dritte Argument ist NULL zugewiesen. Dadurch können Methoden Werte optional zurückgeben.  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a>Aufrufen einer Methode mit einem `out`-Argument

In C# 6 und früheren Versionen müssen Sie eine Variable in einer separaten Anweisung deklarieren, bevor Sie es als ein `out`-Argument übergeben. Das folgende Beispiel deklariert eine Variable namens `number`, bevor sie an die Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) übergeben wird, die versucht, eine Zeichenfolge in eine Zahl umzuwandeln.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

Ab C# 7.0 können Sie in der Argumentliste des Methodenaufrufs anstatt in einer separaten Variablendeklaration die `out`-Variable deklarieren. Dies erzeugt kompakteren, lesbaren Code und verhindert auch, dass Sie versehentlich der Variable vor dem Aufruf der Methode einen Wert zuweisen. Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die `number`-Variable im Aufruf der Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@))) definiert.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

Im vorherigen Beispiel ist die `number`-Variable stark als `int` typisiert. Sie können auch eine implizit typisierte lokale Variable deklarieren, wie es im folgenden Beispiel getan wird.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [Methodenparameter](./method-parameters.md)
