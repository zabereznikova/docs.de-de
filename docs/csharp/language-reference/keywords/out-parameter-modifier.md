---
title: "Modifizierer für out-Parameter (C#-Verweis)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c0686d8bb0dec2a5ea6dd92491e58c93b7ee53a8
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="out-parameter-modifier-c-reference"></a>Modifizierer für out-Parameter (C#-Verweis)
Das Schlüsselwort `out` bewirkt, dass Argumente per Verweis übergeben werden. Dies entspricht dem Schlüsselwort [ref](ref.md), mit Ausnahme davon, dass bei `ref` die Variable initialisiert sein muss, bevor sie übergeben wird. Es ähnelt auch dem Schlüsselwort [in](in-parameter-modifier.md). Allerdings lässt `in` nicht zu, dass die aufgerufene Methode den Argumentwert verändern kann. Um einen Parameter `out` zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode das Schlüsselwort `out` explizit verwenden. Zum Beispiel:  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> Das Schlüsselwort `out` kann auch mit einem generischen Typparameter verwendet werden, um anzugeben, dass der Typparameter kovariant ist. Weitere Informationen zur Verwendung des Schlüsselworts `out` in diesem Kontext finden Sie unter [out (generischer Modifizierer)](out-generic-modifier.md).
  
Variablen, die als `out`-Argumente übergeben wurden, müssen nicht initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden. Die aufgerufene Methode ist jedoch erforderlich, um einen Wert zuzuweisen, bevor die Methode zurückgegeben wird.  
  
Obwohl die Schlüsselwörter `in`, `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur. Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument. Der folgende Code wird z. B. nicht kompiliert:  
  
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
  
 Weitere Informationen zum Übergeben von Arrays finden Sie unter [Übergeben von Arrays mit „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:  
  
-   Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.  
  
-   Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.  

## <a name="declaring-out-arguments"></a>Deklarieren von `out`-Argumenten   

 Das Deklarieren einer Methode mit `out`-Argumenten ist nützlich, wenn eine Methode mehrere Werte zurückgeben soll. Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben. Beachten Sie, dass das dritte Argument Null zugewiesen ist. Dadurch können Methoden Werte optional zurückgeben.  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 Das [Try-Muster](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) umfasst die Rückgabe eines `bool`, um anzugeben, ob ein Vorgang erfolgreich war oder fehlschlug, und die Rückgabe des Werts, der durch den Vorgang in einem `out`-Argument erzeugt wurde. Eine Reihe von Analysemethoden, z.B. [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@))), verwendet dieses Muster.
   
## <a name="calling-a-method-with-an-out-argument"></a>Aufrufen einer Methode mit einem `out`-Argument

In C# 6 und früheren Versionen müssen Sie eine Variable in einer separaten Anweisung deklarieren, bevor Sie es als ein `out`-Argument übergeben. Das folgende Beispiel deklariert eine Variable namens `number`, bevor sie an die Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) übergeben wird, die versucht, eine Zeichenfolge in eine Zahl umzuwandeln.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

Ab C# 7 können Sie in der Argumentliste des Methodenaufrufs anstatt in einer separaten Variablendeklaration die `out`-Variable deklarieren. Dies erzeugt kompakteren, lesbaren Code und verhindert auch, dass Sie versehentlich der Variable vor dem Aufruf der Methode einen Wert zuweisen. Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die `number`-Variable im Aufruf der Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@))) definiert.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
Im vorherigen Beispiel ist die `number`-Variable stark als `int` typisiert. Sie können auch eine implizit typisierte lokale Variable deklarieren, wie es im folgenden Beispiel getan wird.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md)
