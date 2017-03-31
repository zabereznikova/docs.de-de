---
title: unsafe (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
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
ms.openlocfilehash: afedd3d99aea9f73d175fd2957a7d586ebce6d72
ms.lasthandoff: 03/13/2017

---
# <a name="unsafe-c-reference"></a>unsafe (C#-Referenz)
Das Schlüsselwort `unsafe` kennzeichnet einen unsicheren Kontext, der für alle Zeigeroperationen erforderlich ist. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 Sie können bei der Deklaration eines Typs oder Members den Modifizierer `unsafe` verwenden. Daraufhin wird der gesamte Text des Typs oder Members als unsicherer Kontext angesehen. Hier sehen Sie eine Methode, die mit dem Modifizierer `unsafe` deklariert wurde:  
  
```  
  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Der unsichere Kontext erstreckt sich von der Parameterliste bis zum Ende der Methode, weshalb in der Parameterliste auch Zeiger verwendet werden können:  
  
```  
  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 Sie können auch einen unsafe-Block verwenden, um die Verwendung von unsicherem Code in diesem Block zu aktivieren. Zum Beispiel:  
  
```  
  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Um unsicheren Code kompilieren zu können, müssen Sie die Compileroption [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) angeben. Unsicherer Code kann nicht von der Common Language Runtime überprüft werden.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Puffer fester Größe](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
