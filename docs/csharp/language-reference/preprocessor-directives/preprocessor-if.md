---
title: '##if (C#-Referenz) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#if'
dev_langs:
- CSharp
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: 4fc51446d297015d9e492703c9b1868c3b513c53
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="if-c-reference"></a>#if (C#-Referenz)
Wenn der C#-Compiler eine `#if`-Direktive vorfindet, auf die möglicherweise eine [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)-Direktive folgt, wird der Code zwischen den Direktiven nur dann kompiliert, wenn das angegebene Symbol definiert wurde.  Im Gegensatz zu C und C++ können Sie einem Symbol keinen numerischen Wert zuweisen. Die #if-Anweisung in C# ist ein boolescher Ausdruck und überprüft nur, ob das Symbol definiert wurde. Beispiel:  
  
```  
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 Sie können die Operatoren [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (Gleichheit), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (Ungleichheit) nur zur Überprüfung auf [true](../../../csharp/language-reference/keywords/true.md) oder [false](../../../csharp/language-reference/keywords/false.md) verwenden. „True“ bedeutet, dass das Symbol definiert wurde. Die `#if DEBUG`-Anweisung hat die gleiche Bedeutung wie `#if (DEBUG == true)`. Sie können mithilfe der Operatoren [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (und), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (oder) und [!](../../../csharp/language-reference/operators/logical-negation-operator.md) (nicht ) auswerten, ob mehrere Symbole definiert wurden. Symbole und Operatoren können auch mit Klammern gruppiert werden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie `#if` mit den Direktiven [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) und [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) verwenden, können Sie Code je nach dem Vorhandensein eines oder mehrerer Symbole ein- oder ausschließen. Dies kann hilfreich sein, wenn Code für einen Debugbuild oder für eine bestimmte Konfiguration kompiliert wird.  
  
 Eine bedingte Direktive, die mit einer `#if`-Direktive beginnt, muss explizit mit einer `#endif`-Direktive beendet werden.  
  
 Mit `#define` kann ein Symbol definiert werden. Wenn dieses Symbol dann als Ausdruck an die `#if`-Direktive übergeben wird, wird der Ausdruck als `true` ausgewertet.  
  
 Ein Symbol kann auch mit der [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)-Compileroption definiert werden. Die Definition eines Symbols kann mit [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) aufgehoben werden.  
  
 Zwischen einem Symbol, das mit `/define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt. Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.  
  
 Der Gültigkeitsbereich eines mit `#define` erstellten Symbols ist die Datei, in der es definiert wurde.  
  
## <a name="example"></a>Beispiel  
  
```  
// preprocessor_if.cs  
#define DEBUG#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 **DEBUG und MYTEST werden definiert.**   
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
