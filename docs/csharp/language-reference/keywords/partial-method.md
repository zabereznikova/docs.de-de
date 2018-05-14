---
title: partial (Methode) (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 29b5d442a1aa33babc24aee987e749c93a5ec727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="partial-method-c-reference"></a>partial (Methode) (C#-Referenz)
Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert. Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können. Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung. Die folgenden Bedingungen gelten für partielle Methoden:  
  
-   Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.  
  
-   Die Methode muss "void" zurückgeben.  
  
-   Es sind keine Zugriffsmodifizierer zulässig. Partielle Methoden sind implizit privat.  
  
 Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [partial (Typ)](../../../csharp/language-reference/keywords/partial-type.md)
