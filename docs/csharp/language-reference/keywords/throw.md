---
title: throw (C#-Referenz)
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.translationtype: HT
ms.sourcegitcommit: 81117b1419c2a9c3babd6a7429052e2b23e08a70
ms.openlocfilehash: 77f44a43b80c4cf1f12baadaaf6861b3b53244d9
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="throw-c-reference"></a>throw (C#-Referenz)
Signalisiert das Auftreten einer Ausnahme während der Programmausführung.  
  
## <a name="remarks"></a>Hinweise

Die Syntax von `throw` lautet:

```csharp
throw [e]
```
Wo `e` eine Instanz einer Klasse ist, die von <xref:System.Exception?displayProperty=nameWithType> abgeleitet wird. Im folgenden Beispiel wird die `throw`-Anweisung verwendet, um eine @System.IndexOutOfRangeException auszulösen, wenn das Argument, das an eine Methode mit dem Namen `GetNumber` übergeben wurde, nicht auf einen gültigen Index eines internen Arrays reagiert.

[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

Methodenaufrufer verwenden anschließend einen `try-catch`- oder `try-catch-finally`-Block, um die ausgelöste Ausnahme zu behandeln. Im folgenden Beispiel wird die Ausnahme behandelt, die von der Methode `GetNumber` ausgelöst wurde.

[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a>Erneutes Auslösen einer Ausnahme

`throw` kann auch in einem `catch`-Block verwendet werden, um eine Ausnahme erneut auszulösen, die in einem `catch`-Block behandelt wurde.  In diesem Fall verwendet `throw` keinen Operanden für die Ausnahme. Es ist besonders hilfreich, wenn eine Methode ein Argument in einer aufrufenden Funktion an eine andere Bibliotheksmethode übergibt, und die Bibliotheksmethode eine Ausnahme auslöst, die an den Aufrufer übergeben werden muss. Im folgenden Beispiel wird z.B. eine @System.NullReferenceException erneut ausgelöst, die beim Versuch, das erste Zeichen einer deinitialisierten Zeichenfolge abzurufen, ausgelöst wird. 

[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> Sie können auch die `throw e`-Syntax in einem `catch`-Block verwenden, um eine neue Ausnahme zu instanziieren, die Sie an den Aufrufer übergeben. In diesem Fall wird die Stapelüberwachung der ursprünglichen Ausnahme, die von der Eigenschaft @System.Exception.Stacktrace abrufbar ist, nicht beibehalten.
 
## <a name="the-throw-expression"></a>Der `throw`-Ausdruck

Ab C# 7 kann `throw` als Ausdruck sowie als Anweisung verwendet werden. Dadurch wird eine Ausnahme in Kontexten ausgelöst, die zuvor nicht unterstützt wurden. Dazu gehören:

- [Der bedingte Operator](../operators/conditional-operator.md). Im folgenden Beispiel wird ein `throw`-Ausdruck verwendet, um eine @System.ArgumentException auszulösen, wenn eine Methode an ein leeres Zeichenfolgenarray übergeben wird. Diese Logik müsste vor C# 7 in einer `if`/`else`-Anweisung erscheinen.

   [!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- [Der NULL-Sammeloperator](../operators/null-conditional-operator.md). Im folgenden Beispiel wird eine `throw`-Anweisung mit einem NULL-Sammeloperator verwendet, um eine Ausnahme auszulösen, wenn die Zeichenfolge, die einer Eigenschaft `Name` zugewiesen wurde, `null` ist.
 
   [!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- Ein Ausdruckskörper[lambda](../../lambda-expressions.md) oder eine Ausdruckskörpermethode. Das folgende Beispiel veranschaulicht eine Ausdruckskörpermethode, die eine @System.InvalidCastException auslöst, da eine Konvertierung in einen @System.DateTime-Wert nicht unterstützt wird.
 
   [!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Die try-, catch- und throw-Anweisung in C++](../../../csharp/language-reference/keywords/try-catch.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [Vorgehensweise: Explizites Auslösen von Ausnahmen](https://msdn.microsoft.com/library/xhcbs8fz)

