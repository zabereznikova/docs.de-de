---
title: "Modifizierer für out-Parameter (C#-Referenz) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: af1f16016053d3c1b3cae34ff0cb6a3ce8cee9e7
ms.lasthandoff: 03/13/2017

---
# <a name="out-parameter-modifier-c-reference"></a>Modifizierer für out-Parameter (C#-Verweis)
Das Schlüsselwort `out` bewirkt, dass Argumente per Verweis übergeben werden. Dies entspricht dem Schlüsselwort [ref](../../../csharp/language-reference/keywords/ref.md), mit Ausnahme davon, dass bei `ref` die Variable initialisiert sein muss, bevor sie übergeben wird. Um einen Parameter `out` zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode das Schlüsselwort `out` explizit verwenden. Zum Beispiel:  
  
 [!code-cs[cs-out-Schlüsselwort](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> Das Schlüsselwort `out` kann auch mit einem generischen Typparameter verwendet werden, um anzugeben, dass der Typparameter kovariant ist. Weitere Informationen zur Verwendung des Schlüsselworts `out` in diesem Kontext finden Sie unter [out (generischer Modifizierer)](../../../csharp/language-reference/keywords/out-generic-modifier.md).
  
 Variablen, die als `out`-Argumente übergeben wurden, müssen nicht initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden. Die aufgerufene Methode ist jedoch erforderlich, um einen Wert zuzuweisen, bevor die Methode zurückgegeben wird.  
  
 Obwohl die Schlüsselwörter `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur. Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`-Argument übernimmt und die andere ein `out`-Argument. Der folgende Code wird z. B. nicht kompiliert:  
  
```cs
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Überladen ist legal; wenn jedoch eine Methode ein `ref`- oder `out`-Argument übernimmt und die andere keines der beiden, gilt Folgendes:  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 Eigenschaften sind keine Variablen und können daher nicht als `out`-Parameter übergeben werden.  
  
 Weitere Informationen zum Übergeben von Arrays finden Sie unter [Übergeben von Arrays mit „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Sie können keines der beiden Schlüsselwörter `ref` und `out` für die folgenden Methodentypen verwenden:  
  
-   Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.  
  
-   Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.  

## <a name="declaring-out-arguments"></a>Deklarieren von `out`-Argumenten   

 Das Deklarieren einer Methode mit `out`-Argumenten ist nützlich, wenn eine Methode mehrere Werte zurückgeben soll. Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben. Beachten Sie, dass das dritte Argument Null zugewiesen ist. Dadurch können Methoden Werte optional zurückgeben.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 Das [Try-Muster](https://docs.microsoft.com/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) umfasst die Rückgabe eines `bool`, um anzugeben, ob ein Vorgang erfolgreich war oder fehlschlug, und die Rückgabe des Werts, der durch den Vorgang in einem `out`-Argument erzeugt wurde. Eine Anzahl von Analysemethoden, z.B. @System.DateTime.TryParse(System.String,@System.DateTime), verwendet dieses Muster.
   
## <a name="calling-a-method-with-an-out-argument"></a>Aufrufen einer Methode mit einem `out`-Argument

In C# 6 und früheren Versionen müssen Sie eine Variable in einer separaten Anweisung deklarieren, bevor Sie es als ein `out`-Argument übergeben. Im folgenden Beispiel wird eine Variable namens `number` deklariert, bevor sie an die Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,@System.Int32) übergeben wird, die versucht, eine Zeichenfolge in eine Zahl umzuwandeln.

 [!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

Ab C# 7 können Sie in der Argumentliste des Methodenaufrufs anstatt in einer separaten Variablendeklaration die `out`-Variable deklarieren. Dies erzeugt kompakteren, lesbaren Code und verhindert auch, dass Sie versehentlich der Variable vor dem Aufruf der Methode einen Wert zuweisen. Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die `number`-Variable im Aufruf der Methode [Int32.TryParse] (xref:System.Int32.TryParse (System.String,@System.Int32) definiert.

 [!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
Im vorherigen Beispiel ist die `number`-Variable stark als `int` typisiert. Sie können auch eine implizit typisierte lokale Variable deklarieren, wie es im folgenden Beispiel getan wird.

 [!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md)
